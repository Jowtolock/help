# TongWeb安装
>**[info] 建议**
>
>安装前重启一次Web的服务，确保业务重启后可以正常运行，然后再安装云锁防护模块；同时将要修改的配置文件进行备份。

**Web容器使用的Java（jdk或jre）的版本需 1.6 及以上。**

- [Windows安装说明](#windows)
- [Linux安装说明](#linux)

## Windows

假定 TongWeb 的工作目录：`TWNS_HOME=C:\TongWeb5.0`

1）拷贝`jspAgent`目录到`%TWNS_HOME%`下。

2）登录控制台：`http://IP:9060/twns`， 服务器配置->启动参数，新增一项：`-javaagent:%TWNS_HOME%\jspAgent\JSPAgent.jar`或绝对路径的写法：`-javaagent:"C:\TongWeb5.0\jspAgent\JSPAgent.jar`

![](/assets/TongwebW.png)

3）重启TongWeb。

## Linux

假设TongWeb工作目录：`TWNS_HOME=/root/TongWeb5.0`

1）拷贝`jspAgent`目录到`${TWNS_HOME}`下。

2）登录控制台：`http://IP:9060/twns`， 服务器配置->启动参数，新增一项:
`-javaagent:${TWNS_HOME}/jspAgent/JSPAgent.jar`

![](/assets/TongwebL.png)

3）重启TongWeb。