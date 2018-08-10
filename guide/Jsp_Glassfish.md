# Glassfish安装
>**[info] 建议**
>
>安装前重启一次Web的服务，确保业务重启后可以正常运行，然后再安装云锁防护模块；同时将要修改的配置文件进行备份。

**Web容器使用的Java（jdk或jre）的版本需 1.6 及以上。**

- [Windows安装说明](#windows)
- [Linux安装说明](#linux)

## Windows

假设Glassfish的工作目录：`GLASSFISH\_HOME=C:\glassfish4`

1）拷贝`jspAgent`目录到`%GLASSFISH\_HOME%`下。

2）登录Glassfish控制台：`https://IP:4848`，Configurations-&gt;server-config-&gt;JVM]Settings-&gt; JVM Options-&gt;Add JVM Option，新增一项：`-javaagent: C:\glassfish4\jspAgent\JSPAgent.jar`

![](/assets/GlassfishW.png)

3）重启 Glassfish。

## Linux

假设`Glassfish`的工作目录：`GLASSFISH_HOME= /usr/local/glassfish/glassfish`

1）拷贝`jspAgent`目录到`${GLASSFISH\_HOME}`下。

2）登录Glassfish控制台`https://IP:4848`,Configurations-&gt; server-config-&gt;JVM Settings-&gt;JVM Options-&gt;Add JVM Option,新增一项：`-javaagent:/usr/local/glassfish/glassfish/jspAgent/JSPAgent.jar`

![](/assets/GlassfishL.png)

3）重启Glassfish。

