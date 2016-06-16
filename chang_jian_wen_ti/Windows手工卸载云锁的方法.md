## 云锁安装失败，无法再次安装或卸载失败时的解决方法

1.  首次安装云锁，需判断是否安装其它类似安全软件，关闭注册表相关保护进行安装
2.  曾经安装过云锁，则按照如下步骤操作
<br>①先从添加删除程序里卸载云锁
<br>②然后cmd下执行
<br>&emsp;sc stop yunsuoagent
<br>&emsp;sc delete yunsuoagent
<br>&emsp;sc stop yunsuodaemon
<br>&emsp;sc delete yunsuodaemon
<br>&emsp;sc delete resguard
<br>&emsp;sc delete resguard2
<br>&emsp;sc delete secmodel
<br>③执行后重启操作系统，然后再次安装云锁