#### Windows安装说明
##### 2. WebLogic
1）拷贝 jspAgent 目录到 %DOMAIN_HOME% 下。

2）修改 %DOMAIN_HOME%\bin\startWebLogic.cmd， 定位到
set JAVA_OPTIONS=%SAVE_JAVA_OPTIONS%， 在其下追加一行：set JAVA_OPTIONS=-javaagent:%DOMAIN_HOME%\jspAgent\JSPAgent.jar %JAVA_OPTIONS%

![](/assets/Windows_Weblogic_1.png)


3）重启 WebLogic。