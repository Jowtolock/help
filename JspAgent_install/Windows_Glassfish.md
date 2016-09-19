#### 4. Glassfish
##### Windows 安装说明
假设Glassfish的工作目录：GLASSFISH_HOME= C:\glassfish4

1）拷贝 jspAgent 目录到 %GLASSFISH_HOME% 下。

2）登录Glassfish控制台：https://IP:4848，Configurations->server-config->JVM Settings-> JVM Options->Add JVM Option，新增一项 ：
-javaagent: C:\glassfish4\jspAgent\JSPAgent.jar

![](/assets/Windows_Glassfish_1.png)

3）重启 Glassfish。
##### Linux 安装说明
假设Glassfish的工作目录：GLASSFISH_HOME= /usr/local/glassfish/glassfish

1）拷贝jspAgent目录到${GLASSFISH_HOME}下。

2）登录Glassfish 控制台 https://IP:4848， Configurations-> server-config->JVM Settings->JVM Options->Add JVM Option， 

新增一项：-javaagent:/usr/local/glassfish/glassfish/jspAgent/JSPAgent.jar

![](/assets/Linux_Glassfish_1.png)

3）重启Glassfish。