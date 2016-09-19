#### Windows安装说明 
##### 6. Jetty
假定Jetty的工作目录：JETTY_HOME= C:/Program Files (x86)/jetty-distribution-8.1.17/jetty-distribution-8.1.17.v20150415

1）拷贝 jspAgent 目录到 %JETTY_HOME% 下。

2） 启动命令修改：java -jar %JETTY_HOME%\start.jar 修改为 java -javaagent:%JETTY_HOME%\jspAgent\JSPAgent.jar -jar %JETTY_HOME%\start.jar
