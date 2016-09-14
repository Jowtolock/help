#### Linux安装说明
##### 1. Tomcat/Tomee
假设tomcat的工作目录为：CATALINA_HOME=/usr/local/tomcat/

1）拷贝jspAgent 目录到 ${CATALINA_HOME} 下。

![](/assets/Linux_Tomcat_1.png)

2）修改${CATALINA_HOME}/bin/catalina.sh中的JAVA启动参数，附加上 -javaagent选项。过程如下：定位到elif [ "$1" = "start" ] ; then，其下追加一行：JAVA_OPTS="-javaagent:${CATALINA_HOME}/jspAgent/JSPAgent.jar ${JAVA_OPTS}"

![](/assets/Linux_Tomcat_2.png)

3）重启tomcat。