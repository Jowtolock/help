# Jboss/wildfly 安装
>**建议:安装前重启一次Web的服务，确保业务重启后可以正常运行，然后再安装云锁防护模块；同时将要修改的配置文件进行备份。**

## Windows 安装说明

1）拷贝`jspAgent`目录到`%JBOSS_HOME%`下。

2）根据你自己的使用模式，修改`%JBOSS_HOME %/bin/standalone.ba`t或者`%JBOSS_HOME %/bin/domain.bat`中JAVA启动参数，定位到`:RESTART`，在其上进行添加。

如`:RESTART`下`"%JAVA%" %JAVA_OPTS%`，则添加`set "JAVA_OPTS=-javaagent:C:\jspAgent\JSPAgent.jar %JAVA_OPTS%"`


![](/assets/W_Jboss_1.png)

如`:RESTART`下`"%JAVA%" %PROCESS_CONTROLLER_JAVA_OPTS%`，则添加`set "PROCESS_CONTROLLER_JAVA_OPTS=-javaagent:C:\jspAgent\JSPAgent.jar %PROCESS_CONTROLLER_JAVA_OPTS%"`


![](/assets/W_Jboss_2.png)

**注意：`"%JAVA%"`后的参数不是固定的，配置文件中`"%JAVA%"`跟着是什么参数，在添加的时候`set`后面就跟着什么参数。**

3）重启Jboss。

## linux 安装说明

假设Jboss工作目录：`JBOSS_HOME=/root/jboss-as-7.1.1.Final`

1）拷贝`jspAgent`目录到`$JBOSS_HOME`下。

2）根据你自己的使用模式，修改`$JBOSS_HOME/bin/standalone.sh`或者 `$JBOSS_HOME/bin/domain.sh`中JAVA启动参数，定位字符串`# Display our environment`，在其上追加一行：`JAVA_OPTS="-javaagent:$JBOSS_HOME/jspAgent/JSPAgent.jar $JAVA_OPTS"`

![](/assets/Linux_Jboss_1.png)

3）重启Jboss。



