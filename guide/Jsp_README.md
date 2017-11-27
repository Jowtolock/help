#### RASP使用说明
**注意：**由于安装完成后需重启Web服务，所以线上业务尽量选取在用户访问量较少的时段内安装。同时建议安装前重启一次Web的服务，确保业务重启后可以正常运行，然后再安装云锁防护模块。

JSPAgent主要针对Struts2漏洞（远程执行和文件上传）、WebLogic对象反序列化漏洞、命令执行漏洞、任意文件读取漏洞、文件上传漏洞、SQL注入漏洞和WebShell等漏洞进行识别及防护。

安装时，云锁安装包会提供一个名为JspAgent的目录，目录结构为

**Windows：**
`/jspAgent/JSPAgent.jar、/jspAgent/JSPAgent.dll、/jspAgent/msvcp100.dll、/jspAgent/msvcr100.dll、/jspAgent/litexml.dll、/jspAgent/x64/JSPAgent.dll、/jspAgent/x64/msvcp100.dll、/jspAgent/x64/msvcr100.dll、/jspAgent/x64/litexml.dll`

**Linux：**

`/jspAgent/JSPAgent.jar、/jspAgent/libJSPAgent.so、/jspAgent/liblitexml_linux.so`

#### 升级说明
当JspAgent更新时，云锁会在更新公告中进行说明；除此外云锁安装后在JspAgent生成一个记录文件md5的文档，当更新后的文档中md5值与原文件中的md5值不一致时也表示JspAgent更新了。更新时需按照以下步骤进行：

1. 暂停当前运行的Java服务

2. 用云锁目录下的JspAgent目录替换掉Java路径下的JspAgent目录，具体方法参照安装步骤。

3. 启动Java服务
