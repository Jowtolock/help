#### Nginx自编译步骤
**建议：**在安装防护模块前先重启一次Nginx的服务，确保业务重启后可以正常运行，然后再安装云锁防护模块。

1. 编译前先将已经安装的Nginx文件进行备份
       # cd /usr/local/nginx/sbin/
       # cp nginx nginx.bak
![](/assets/Nginx filter_1.png)
2. 有源码包则忽略此步骤。无源码包则到Nginx官网[(http://nginx.org/en/download.html)](http://nginx.org/en/download.html)下载Nginx源码包，源码包需与自己的当前Nginx版本匹配（假设当前Nginx版本为1.10）
       # wget http://nginx.org/download/nginx-1.10.1.tar.gz
![](/assets/Nginx filter_2.png)
3. 解压nginx源码包
       # tar zxvf nginx-1.11.4.tar.gz
4. 