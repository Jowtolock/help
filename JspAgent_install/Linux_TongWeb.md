#### Linux安装说明
##### 5. TongWeb
假设TongWeb工作目录：TWNS_HOME=/root/TongWeb5.0

1）拷贝jspAgent目录到${TWNS_HOME}下。

2）登录控制台：http://IP:9060/twns， 服务器配置->启动参数，新增一项：
-javaagent:${TWNS_HOME}/jspAgent/JSPAgent.jar

![](/assets/Linux_Tongweb_1.png)

3）重启TongWeb。
