## 云锁通过卸载程序卸载失败时，手工卸载的方法

1.  cmd下执行以下命令：

sc stop yunsuoagent

sc delete yunsuoagent

sc stop yunsuodaemon

sc delete yunsuodaemon

sc delete resguard

sc delete resguard2

sc delete secmodel

1.  删除云锁安装目录
2.  重启操作系统