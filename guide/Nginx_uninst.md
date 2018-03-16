# 卸载 Nginx/Tengine 防护模块
1. 使用nginx.bak文件替换掉自编译的nginx文件，替换后重启Nginx
      
   ```
   # cd /usr/local/nginx/sbin/ 
   # rm -rf nginx
   # mv nginx.bak nginx
   ```
   
2. 删除文件
 
   手动删除或者重命名`/usr/local/yunsuo_agent/nginx/`目录下的 `libnginx_plugin.so`（此操作需要关闭云锁自保护功能）， 重启nginx服务即可`"service nginx restart"`。 