#### JspAgent安装说明
##### 一、 简介
JSPAgent 主要功能有两项：

1、 漏洞防护功能 ：

	1） 针对 Struts2 远程命令执行和文件上传漏洞的防护。
	2） 针对 WebLogic 对象反序列化漏洞的防护。
	3） 针对命令执行漏洞的防护
	4） 针对任意文件读取漏洞的防护
	5） 针对文件上传漏洞的防护
	6） 针对SQL注入漏洞的防护

2、 动态（基于行为）识别JSP 类型的Webshell。

    注意 ： 
    1、Web容器使用的Java(jdk或jre)的版本需1.6 及 以上。
    2、SQL注入防护目前支持的数据库包括：Mysql、 Oracle、 Sqlserver、 Postgresql 四种。
