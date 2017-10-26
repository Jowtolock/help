#### 卸载Nginx/Tengine防护模块
1.  使用nginx.bak文件替换掉自编译的nginx文件
      
 ```
 # cd /usr/local/nginx/sbin/ 
 # rm -rf nginx
 # cp nginx.bak nginx
 ```

 ![](/assets/Nginx filter_12.png)

2. 删除文件
 
 手动删除或者重命名`/usr/local/yunsuo_agent/nginx/`目录下的 `libnginx_plugin.so`（此操作需要关闭云锁自保护功能）， 重启nginx服务即可`"service nginx restart"`。 

3. 使用原文件替换
    
 手动使用系统原有的nginx直接替换当前使用的带有云锁防护模块的nginx。