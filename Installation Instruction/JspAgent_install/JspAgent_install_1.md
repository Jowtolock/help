#### JspAgent安装说明

##### Windows安装说明
**1. Tomcat/Tomee**

官网 tomcat 版本

假设 tomcat 工作目录 ：CATALINA_HOME =C:\Program Files\Apache Software Foundation\Tomcat 6.0

1）拷贝 jspAgent 目录到 %CATALINA_HOME% 下。

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
