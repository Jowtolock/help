#### Linux安装说明
##### 6. Jetty
假设Jetty的工作目录：JETTY_HOME= /usr/local/jetty

1）拷贝jspAgent目录到$JETTY_HOME下。

2）启动命令修改：java -jar $JETTY_HOME/start.jar修改为java -javaagent:$JETTY_HOME/jspAgent/JSPAgent.jar -jar $JETTY_HOME/start.jar
