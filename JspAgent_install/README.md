#### JspAgent安装说明

##### 简介

JSPAgent 主要功能有两项：

1、 漏洞防护功能 ：

```
1） 针对 Struts2 远程命令执行和文件上传漏洞的防护。
2） 针对 WebLogic 对象反序列化漏洞的防护。
3） 针对命令执行漏洞的防护
4） 针对任意文件读取漏洞的防护
5） 针对文件上传漏洞的防护
6） 针对SQL注入漏洞的防护
```

2、 动态（基于行为）识别JSP 类型的Webshell。

```
注意 ： 
1、Web容器使用的Java(jdk或jre)的版本需1.6 及 以上。
2、SQL注入防护目前支持的数据库包括：Mysql、 Oracle、 Sqlserver、 Postgresql 四种。
```

##### 工作原理

利用 JAVA 虚拟机 启动选项 ：-javaagent， 使 jspAgent.jar 可以跟踪处理 web 请求上下文， 并针对可疑行为， 做出相应的动作。

##### 安装说明

云锁安装包会提供一个名为JspAgent的目录，目录结构：
	
    Linux 版：
        /jspAgent/JSPAgent.jar
        /jspAgent/libJSPAgent.so
        /jspAgent/liblitexml_linux.so
    Windows 版：
        /jspAgent/JSPAgent.jar
        /jspAgent/JSPAgent.dll
        /jspAgent/msvcp100.dll
        /jspAgent/msvcr100.dll
        /jspAgent/litexml.dll
        /jspAgent/x64/JSPAgent.dll
        /jspAgent/x64/msvcp100.dll
        /jspAgent/x64/msvcr100.dll
        /jspAgent/x64/litexml.dll


