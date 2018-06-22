# WebSphere安装

>**[info] 建议
>
>安装前重启一次Web的服务，确保业务重启后可以正常运行，然后再安装云锁防护模块；同时将要修改的配置文件进行备份。

**Web容器使用的Java（jdk或jre）的版本需 1.6 及以上。**

- [Windows安装说明](#windows)
- [Linux安装说明](#linux)

## Windows

1）拷贝`jspAgent`目录到`c:`下。

2） 打开`dmgr`控制台，服务器->服务器类型->`WebSphere Application Server`

![](/assets/WebSphereW01.png)

3）点进你要配置`javaagent`的`Server`

![](/assets/WebSphereW02.png)

4）配置->服务器基础结构->`Java`和进程管理->进程定义

![](/assets/WebSphereW03.png)

5）其他属性->`Java`虚拟机

![](/assets/WebSphereW04.png)

6）通用`JVM`参数：配置`javaagent`

![](/assets/WebSphereW05.png)

7）保存到主配置

![](/assets/WebSphereW06.png)

8）重启`Server`：建议从服务端手动重启，以便当时查看是否出错，通常是
```
stopServer.bat Server
start Server.bat Server
```

![](/assets/WebSphereW07.png)