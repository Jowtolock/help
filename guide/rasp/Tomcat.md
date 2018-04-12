# Tomcat/Tomee安装
>**[info] 建议**
>
>安装前重启一次Web的服务，确保业务重启后可以正常运行，然后再安装云锁防护模块；同时将要修改的配置文件进行备份。

**Web容器使用的Java（jdk或jre）的版本需 1.6 及以上。**

- [Windows](#Windows安装说明)
 - [官网Tomcat](#官网Tomcat)
 - [JTM套件](#JTM套件)
 - [其它版本](#其它版本)
- [Linux](#Linux安装说明)

## Windows安装说明

### 官网Tomcat

假设 tomcat 工作目录：`CATALINA_HOME =C:\Program Files\Apache Software Foundation\Tomcat 6.0`

1）拷贝`JspAgent`目录到`%CATALINA_HOME%`下。

2）修改JAVA启动参数：注册表中Options的值
    
    x86:HKEY_LOCAL_MACHINE\SOFTWARE\Apache Software Foundation\Procrun 2.0\tomcat6\Parameters\Java
    x64:HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Apache Software Foundation\Procrun 2.0\tomcat6\Parameters\Java
修改如下

    -Dcatalina.home=C:\Program Files\Apache Software Foundation\Tomcat 6.0
    -Dcatalina.base=C:\Program Files\Apache Software Foundation\Tomcat 6.0
    -Djava.endorsed.dirs=C:\Program Files\Apache Software Foundation\Tomcat 6.0\endorsed
    -Djava.io.tmpdir=C:\Program Files\Apache Software Foundation\Tomcat 6.0\temp
    -Djava.util.logging.manager=org.apache.juli.ClassLoaderLogManager
    -Djava.util.logging.config.file=C:\Program Files\Apache Software Foundation\Tomcat6.0\conf\logging.properties
    ------追加下面这一行---
    -javaagent:C:\Program Files\Apache Software Foundation\Tomcat 6.0\jspAgent\JSPAgent.jar

![](/assets/TomcatW01.png)

3）重启 tomcat。

### JTM套件

假定tomcat的工作目录：`CATALINA_HOME=C:\JTM\tomcat`

1）拷贝`jspAgent`目录到`%CATALINA_HOME%`下。

2）修改JAVA启动参数：`%CATALINA_HOME%\bin\service.bat`中，定位`++JvmOptions`，追加`-javaagent:%CATALINA_HOME%\jspAgent\JSPAgent.jar;`

形如 ：

`"%EXECUTABLE%" //US//%SERVICE_NAME% ++JvmOptions "-Djava.io.tmpdir=%CATALINA_BASE%\temp;-Djava.util.logging.manager=org.apache.juli.ClassLoaderLogManager;-Djava.util.logging.config.file=%CATALINA_BASE%\conf\logging.properties" --JvmMs 128 --JvmMx 512 --Startup=auto`

修改为 ：

`"%EXECUTABLE%" //US//%SERVICE_NAME% ++JvmOptions "*-javaagent:%CATALINA_HOME%\jspAgent\JSPAgent.jar;*-Djava.io.tmpdir=%CATALINA_BASE%\temp;-Djava.util.logging.manager=org.apache.juli.ClassLoaderLogManager;-Djava.util.logging.config.file=%CATALINA_BASE%\conf\logging.properties" --JvmMs 128 --JvmMx 512 --Startup=auto`

![](/assets/TomcatW02.png)

3）重启 tomcat 。

### 其他版本

观察tomcat的启动脚本，如果最终调用了`%CATALINA_HOME%/bin/catalina.bat`，那么可以在这个文件中修改，定位到：`execCmd`，在其下追加一行：

`set JAVA_OPTS=-javaagent:%CATALINA_HOME%\jspAgent\JSPAgent.jar  %JAVA_OPTS%`

![](/assets/TomcatW03.png)

## Linux安装说明

假设tomcat的工作目录为：`CATALINA_HOME=/usr/local/tomcat/`

1）拷贝`jspAgent`目录到`${CATALINA_HOME}`下。

![](/assets/TomcatL01.png)

2）修改`${CATALINA_HOME}/bin/catalina.sh`中的JAVA启动参数，附加上`-javaagent`选项。过程如下：定位到`elif [ "$1" = "start" ]; then`，其下追加一行：`JAVA_OPTS="-javaagent:${CATALINA_HOME}/jspAgent/JSPAgent.jar ${JAVA_OPTS}"`

![](/assets/TomcatL02.png)

3）重启tomcat。