# Jetty 安装

> **\[info] 建议**
>
> 安装前重启一次Web的服务，确保业务重启后可以正常运行，然后再安装云锁防护模块；同时将要修改的配置文件进行备份。

**Web容器使用的Java（jdk或jre）的版本需 1.6 及以上，暂不支持“敏感词过滤”和“防多线程下载”功能。**

* [Windows安装说明](jetty.md#windows)
* [Linux安装说明](jetty.md#linux)

## Windows

假定Jetty的工作目录：`JETTY_HOME= C:/Program Files (x86)/jetty-distribution-8.1.17/jetty-distribution-8.1.17.v20150415`

1）拷贝`jspAgent`目录到`%JETTY_HOME%`下。

2） 启动命令修改：`java -jar %JETTY_HOME%\start.jar`修改为`java -javaagent:%JETTY_HOME%\jspAgent\JSPAgent.jar -jar %JETTY_HOME%\start.jar`

## Linux

假设Jetty的工作目录：`JETTY_HOME=/usr/local/jetty`

1）拷贝`jspAgent`目录到`$JETTY_HOME`下。

2）启动命令修改：`java -jar $JETTY_HOME/start.jar`修改为`java -javaagent:$JETTY_HOME/jspAgent/JSPAgent.jar -jar $JETTY_HOME/start.jar`
