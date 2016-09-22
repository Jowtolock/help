##### 卸载Nginx防护模块

1.  通过PC端卸载
    
 将安装时备份的nginx.bak文件复制到云锁nginx目录的backup目录下，覆盖原有nginx.bak文件。这样就可以在云锁PC端直接卸载了。
   
        # cd /usr/local/nginx/sbin/
        # rm -rf /usr/local/yunsuo_agent/nginx/backup/nginx.bak
        # cp nginx.bak /usr/local/yunsuo_agent/nginx/backup

2. 删除文件
   
 手动删除或者重命名/usr/local/yunsuo_agent/nginx/目录下的 libnginx_plugin.so（此操作需要关闭云锁自保护功能）， 重启nginx服务即可`"service nginx restart"`。

3. 使用原文件替换
    
 手动使用系统原有的nginx直接替换当前使用的带有云锁防护模块的nginx。