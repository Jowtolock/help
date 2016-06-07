## WDCP卸载云锁后，后台登录失败的问题 {#wdcp}

可能是卸载云锁导致WDCP后台的Apache停止运行导致的，重新启动一下wdcp后台的Apache程序即可。启动命令：/www/wdlinux/wdapache/bin/httpd –k start