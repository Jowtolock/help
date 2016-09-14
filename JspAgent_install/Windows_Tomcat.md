#### JspAgent安装说明 
##### Windows安装说明
###### 1. Tomcat/Tomee
**官网 Tomcat 版本**

假设 tomcat 工作目录：CATALINA_HOME =C:\Program Files\Apache Software Foundation\Tomcat 6.0

1）拷贝JspAgent目录到%CATALINA_HOME%下。

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

![](/assets/Windows_Tomcat_1.png)

3）重启 tomcat。

**JTM 套件**

假定 tomcat的工作目录 ：CATALINA_HOME=C:\JTM\tomcat

1）拷贝 jspAgent 目录到 %CATALINA_HOME% 下。

2）修改JAVA 启动参数：%CATALINA_HOME%\bin\service.bat中，定位++JvmOptions，追加-javaagent:%CATALINA_HOME%\jspAgent\JSPAgent.jar;

形如 ：

"%EXECUTABLE%" //US//%SERVICE_NAME% ++JvmOptions "-Djava.io.tmpdir=%CATALINA_BASE%\temp;-Djava.util.logging.manager=org.apache.juli.ClassLoaderLogManager;-Djava.util.logging.config.file=%CATALINA_BASE%\conf\logging.properties" --JvmMs 128 --JvmMx 512 --Startup=auto

修改为 ：

"%EXECUTABLE%" //US//%SERVICE_NAME% ++JvmOptions "*-javaagent:%CATALINA_HOME%\jspAgent\JSPAgent.jar;*-Djava.io.tmpdir=%CATALINA_BASE%\temp;-Djava.util.logging.manager=org.apache.juli.ClassLoaderLogManager;-Djava.util.logging.config.file=%CATALINA_BASE%\conf\logging.properties" --JvmMs 128 --JvmMx 512 --Startup=auto

![](/assets/Windows_Tomcat_2.png)

3）重启 tomcat 。

**其他版本**

观察tomcat的启动脚本，如果最终调用了%CATALINA_HOME%/bin/catalina.bat，那么可以在这个文件中修改，定位到：execCmd，在其下追加一行：

`set JAVA_OPTS=-javaagent:%CATALINA_HOME%\jspAgent\JSPAgent.jar  %JAVA_OPTS%`

![](/assets/Windows_Tomcat_3.png)