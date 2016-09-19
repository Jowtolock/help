#### 6. Jetty 
##### Windows 安装说明
假定Jetty的工作目录：JETTY_HOME= C:/Program Files (x86)/jetty-distribution-8.1.17/jetty-distribution-8.1.17.v20150415

1）拷贝 jspAgent 目录到 %JETTY_HOME% 下。

2） 启动命令修改：java -jar %JETTY_HOME%\start.jar 修改为 java -javaagent:%JETTY_HOME%\jspAgent\JSPAgent.jar -jar %JETTY_HOME%\start.jar

##### Linux 安装说明

假设Jetty的工作目录：JETTY_HOME=/usr/local/jetty

1）拷贝jspAgent目录到$JETTY_HOME下。

2）启动命令修改：java -jar $JETTY_HOME/start.jar修改为java -javaagent:$JETTY_HOME/jspAgent/JSPAgent.jar -jar $JETTY_HOME/start.jar