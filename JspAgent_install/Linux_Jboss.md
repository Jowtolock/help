#### Linux安装说明
##### 3. Jboss/wildfly
假设Jboss工作目录：JBOSS_HOME=/root/jboss-as-7.1.1.Final

1）拷贝jspAgent目录到$JBOSS_HOME下。

2）根据你自己的使用模式，修改$JBOSS_HOME/bin/standalone.sh或者 $JBOSS_HOME/bin/domain.sh中JAVA启动参数，定位字符串# Display our environment，在其上追加一行：JAVA_OPTS="-javaagent:$JBOSS_HOME/jspAgent/JSPAgent.jar $JAVA_OPTS"

![](/assets/Linux_Jboss_1.png)

3）重启Jboss。
