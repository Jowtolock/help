# Nginx/Tengine 自编译说明

除了采用内核加固技术来增强服务器自身对抗恶意代码和黑客攻击的策略外，云锁通过在web中间件部署安全模块的方式来对抗网络攻击，通过安全模块的fliter过滤功能,云锁能高效过滤恶意流量和黑客攻击，强力对抗CC、SQL注入、上传一句木马等网络攻击。

一般情况下，当用户安装云锁的时候，云锁会自动适配nginx版本，使用我们已经预编译好的包含防护模块的nginx文件替换掉您当前系统中使用的nginx文件。卸载时，会将备份的系统原始nginx文件替换回来。因此，云锁可保护使用nginx搭建的网站，开创了这个领域的先河。

但当nginx更新后，云锁未及时适配最新的nginx版本，或用户的nginx添加（--add-moudel）了第三方模块时需要用户手工加载云锁的防护模块进行防护。通常在安装时云锁会提示存在第三方模块，且PC端也会有显示需要编译。

## 安装

**建议：**在安装防护模块前先重启一次Nginx的服务，确保业务重启后可以正常运行，然后再安装云锁防护模块。

1. 编译前先将已经安装的Nginx文件进行备份，通过ps命令查看nginx文件的路径。以下所有步骤都以自身nginx路径为准。

   ```
   # ps -elf | grep nginx
   ```

   ![](/assets/Nginx filter_0.png)

   ```
   # cd /usr/local/nginx/sbin/
   # cp nginx nginx.bak
   ```

   ![](/assets/Nginx filter_1.png)

2. 过步骤1查看的路径跟-v参数查看当前Nginx版本，如有源码包则忽略此步骤。无源码包则到[Nginx官网](http://nginx.org/en/download.html)下载Nginx源码包，源码包需与自己的当前Nginx版本匹配（假设当前Nginx版本为1.10）。宝塔面板Nginx源码路径：/www/server/nginx/src/。
  
   ```
   # /usr/local/nginx/sbin/nginx -v
   ```

   ![](/assets/Nginx filter_2.1.png)

   ```
   # wget http://nginx.org/download/nginx-1.10.1.tar.gz
   ```

   ![](/assets/Nginx filter_2.2.png)

3. 解压nginx源码包

   ```
   # tar zxvf nginx-1.10.1.tar.gz
   ```

   ![](/assets/Nginx filter_3.png)

4. 由于其默认不支持post过滤，所以需要修改Nginx文件。1.8.0 版本以下修改源码目录下ngx\_http\_upstream.c文件（Nginx 1.8.0 及以上版本和**Tengine**跳过该步骤）。在`static void ngx_http_upstream_init_request(ngx_http_request_t \*r);`行上方添加：`int ngx_http_yunsuo_post_in_handler(ngx_http_request_t *r);`和在`ngx_http_upstream_init_request`后，添加：

   ```
   if (ngx_http_yunsuo_post_in_handler(r)) {
       return;
   }

   # cd nginx-1.10.1/src/http/
   # vi ngx_http_upstream.c
   --------------------下面这段是添加的----------------
   int
   ngx_http_yunsuo_post_in_handler(ngx_http_request_t *r);
   --------------------------------------------------
   static void
   ngx_http_upstream_init_request(ngx_http_request_t *r)
   {
   ngx_str_t                      *host;
   ngx_uint_t                      i;
   ngx_resolver_ctx_t             *ctx, temp;
   ngx_http_cleanup_t             *cln;
   ngx_http_upstream_t            *u;
   ngx_http_core_loc_conf_t       *clcf;
   ngx_http_upstream_srv_conf_t   *uscf, **uscfp;
   ngx_http_upstream_main_conf_t  *umcf;
   --------------------下面这段是添加的----------------
   if (ngx_http_yunsuo_post_in_handler(r)) {
       return;
   }
   --------------------------------------------------
   if (r->aio) {
       return;
   }
   ```

   ![](/assets/Nginx filter_4.png)

5. 下载云锁防护模块压缩包

   ```
   # cd /root/
   # wget https://codeload.github.com/yunsuo-open/nginx-plugin/zip/master -O nginx-plugin-master.zip
   ```

   ![](/assets/Nginx filter_5.png)

6. 解压云锁防护模块压缩包nginx-plugin-master.zip

   ```
   # unzip nginx-plugin-master.zip
   ```

   ![](/assets/Nginx filter_6.png)

7. 获取当前云锁模块所在目录的全路径

   ```
   # cd nginx-plugin-master/
   # pwd
   ```

   ![](/assets/Nginx filter_7.png)

8. 查看当前nginx加载的模块，在编译加载云锁防护模块的时候仍需加载这些模块

   ```
   # /usr/local/nginx/sbin/nginx –V
   ```

   ![](/assets/Nginx filter_8.png)

9. 进入nginx源码目录，对nginx进行编译；编译时在第8步获取的nginx原有模块后添加云锁防护模块，模块路径为第7步获取的云锁防护模块源码全路径“/root/nginx-plugin-master”

   ```
   # cd nginx-1.10.1/
   # ./configure --prefix=/usr/local/nginx --with... --add-module=/root/nginx-plugin-master
   ```

   ![](/assets/Nginx filter_9.1.png)

10. Nginx1.8.0 以上和 Tengine 2.1.2 则需要修改objs/Makefile文件来支持post过滤，在Makefile文件中的`CFLAGS=...-Werror -g`后追加宏定义 `-DHIGHERTHAN8`

   ```
   # vi objs/Makefile
   CFLAGS =  -pipe  -O -W -Wall -Wpointer-arith -Wno-unused-parameter -Werror -g -DHIGHERTHAN8
   ```

   ![](/assets/Nginx filter_9.2.png)

11. configure完成后进行make（如原本无nginx，make后还需make install）

   ```
   # make
   ```

   ![](/assets/Nginx filter_9.3.png)

12. make完成后将系统中原有的nginx用重新编译生成的nginx文件替换，替换后重启nginx使新编译nginx生效

    ```
    # rm -rf /usr/local/nginx/sbin/nginx
    # cp objs/nginx /usr/local/nginx/sbin/
    # service nginx restart
    ```

    ![](/assets/Nginx filter_10.png)

13. 到此通过PC端连接到服务器端，在PC端的界面上可以看到已识别nginx插件。

    ![](/assets/Nginx filter_12.png)
    

 




安装 Nginx/Tengine 防护模块
云锁适配Nginx版本，是使用已经预编译好的包含云锁模块的Nginx替换掉您当前系统中使用的Nginx。但当您的Nginx含有以下参数时，需编译安装。
--add-module、--with-file-aio、--with-http_xslt_module、--with-http_image_filter_module、--with-http_geoip_module、--with-http_perl_module、--with-perl_modules_path、--with-perl、--with-google_perftools_module、--add-dynamic-module、--with-stream=dynamic

建议：在安装防护模块前先重启一次Nginx的服务，确保业务重启后可以正常运行，然后再安装云锁防护模块。
编译前先将已经安装的Nginx文件进行备份，通过ps命令查看nginx文件的路径。以下所有步骤都以自身nginx路径为准。
# ps -elf | grep nginx


# cd /usr/local/nginx/sbin/
# cp nginx nginx.bak


过步骤1查看的路径跟-v参数查看当前Nginx版本，如有源码包则忽略此步骤。无源码包则到Nginx官网下载Nginx源码包，源码包需与自己的当前Nginx版本匹配（假设当前Nginx版本为1.10）。宝塔面板Nginx源码路径：/www/server/nginx/src/。
# /usr/local/nginx/sbin/nginx -v


# wget http://nginx.org/download/nginx-1.10.1.tar.gz


解压nginx源码包
# tar zxvf nginx-1.10.1.tar.gz


由于其默认不支持post过滤，所以需要修改Nginx文件。1.8.0 版本以下修改源码目录下ngx_http_upstream.c文件（Nginx 1.8.0 及以上版本和Tengine跳过该步骤）。在static void ngx_http_upstream_init_request(ngx_http_request_t \*r);行上方添加：int ngx_http_yunsuo_post_in_handler(ngx_http_request_t *r);和在ngx_http_upstream_init_request后，添加：
if (ngx_http_yunsuo_post_in_handler(r)) {
    return;
}

# cd nginx-1.10.1/src/http/
# vi ngx_http_upstream.c
--------------------下面这段是添加的----------------
int
ngx_http_yunsuo_post_in_handler(ngx_http_request_t *r);
--------------------------------------------------
static void
ngx_http_upstream_init_request(ngx_http_request_t *r)
{
ngx_str_t                      *host;
ngx_uint_t                      i;
ngx_resolver_ctx_t             *ctx, temp;
ngx_http_cleanup_t             *cln;
ngx_http_upstream_t            *u;
ngx_http_core_loc_conf_t       *clcf;
ngx_http_upstream_srv_conf_t   *uscf, **uscfp;
ngx_http_upstream_main_conf_t  *umcf;
--------------------下面这段是添加的----------------
if (ngx_http_yunsuo_post_in_handler(r)) {
    return;
}
--------------------------------------------------
if (r->aio) {
    return;
}


下载云锁防护模块压缩包
# cd /root/
# wget https://codeload.github.com/yunsuo-open/nginx-plugin/zip/master -O nginx-plugin-master.zip


解压云锁防护模块压缩包nginx-plugin-master.zip
# unzip nginx-plugin-master.zip


获取当前云锁模块所在目录的全路径
# cd nginx-plugin-master/
# pwd


查看当前nginx加载的模块，在编译加载云锁防护模块的时候仍需加载这些模块
# /usr/local/nginx/sbin/nginx –V


进入nginx源码目录，对nginx进行编译；编译时在第8步获取的nginx原有模块后添加云锁防护模块，模块路径为第7步获取的云锁防护模块源码全路径“/root/nginx-plugin-master”
# cd nginx-1.10.1/
# ./configure --prefix=/usr/local/nginx --with... --add-module=/root/nginx-plugin-master


Nginx1.8.0 以上和 Tengine 2.1.2 则需要修改objs/Makefile文件来支持post过滤，在Makefile文件中的CFLAGS=...-Werror -g后追加宏定义 -DHIGHERTHAN8

# vi objs/Makefile
CFLAGS =  -pipe  -O -W -Wall -Wpointer-arith -Wno-unused-parameter -Werror -g -DHIGHERTHAN8


configure完成后进行make（如原本无nginx，make后还需make install）
# make


make完成后将系统中原有的nginx用重新编译生成的nginx文件替换，替换后重启nginx使新编译nginx生效
# rm -rf /usr/local/nginx/sbin/nginx
# cp objs/nginx /usr/local/nginx/sbin/
# service nginx restart


到此通过PC端连接到服务器端，在PC端的界面上可以看到已识别nginx插件。
