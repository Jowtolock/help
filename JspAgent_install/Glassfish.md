#### Windows安装说明
##### 4. Glassfish
假设Glassfish的工作目录：GLASSFISH_HOME= C:\glassfish4

1）拷贝 jspAgent 目录到 %GLASSFISH_HOME% 下。

2）登录Glassfish控制台：https://IP:4848，Configurations->server-config->JVM Settings-> JVM Options->Add JVM Option，新增一项 ：
-javaagent: C:\glassfish4\jspAgent\JSPAgent.jar

![](/assets/Windows_Glassfish_1.png)

3）重启 Glassfish。

