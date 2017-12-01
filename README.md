云锁是服务器必备安全防护及运维管理SAAS解决方案，支持windows/linux服务器跨平台实时、批量、远程安全管理。云锁会7\*24小时无间断守护业务系统，持续对企业业务系统进行学习并识别业务的风险点，通过防御模块减少风险面，在检测到未知威胁和业务资产变更时，能自动调整安全策略,帮助用户有效抵御CC攻击、SQL注入、XSS跨站攻击、溢出攻击、暴力破解、提权等黑客攻击，及病毒、木马、后门等恶意代码。发生安全事件后，云锁能自动回溯攻击过程，并形成事件分析报告，为企业提供入侵取证及攻击源分析的能力。进而形成“业务资产管理 - 风险识别 - 安全防御 - 威胁感知 - 攻击事件回溯”的一体化安全防御体系。

当前主要提供云锁使用过程中常见的一些问题及解决方法。

以下为云锁支持的功能及费用说明。

##### 基础功能
![](/assets/q_03_1.png)
##### 增值功能
|增值功能|费用|
|-|-|
|[基础资源](http://help.yunsuo.com.cn/manual/f01.html)|10.00 元 / 台|
|[高级防护](http://help.yunsuo.com.cn/manual/f16.html)|150.00 元 / 月 / 台|
|[实时监控](http://help.yunsuo.com.cn/manual/f05.html)|3.00 元 / 月 / 账户|
|[网站性能监控](http://help.yunsuo.com.cn/manual/f26.html)|3.00 元 / 月 / 账户|
|[边界管理](http://help.yunsuo.com.cn/manual/f28.html)|1000.00 元 / 月 / 账户|
|[事件管理](http://help.yunsuo.com.cn/manual/f29.html)|150.00 元 / 月 / 账户|

# 目录

## 入门指南
* [1. 云锁安装说明](/guide/inst_README.md)
   * [1.1 Windows服务器端](/guide/Win_inst.md)
   * [1.2 Linux服务器端](/guide/Lin_inst.md)
   * [1.3 PC端](/guide/PC_inst.md)
* [2. JspAgent使用说明](/guide/Jsp_README.md) 
   * [2.1 Tomcat\/Tomee](/guide/Jsp_Tomcat.md)
   * [2.2 Weblogic](/guide/Jsp_Weblogic.md)
   * [2.3 Jboss\/wildfly](/guide/Jsp_Jboss.md)
   * [2.4 Glassfish](/guide/Jsp_Glassfish.md)
   * [2.5 TongWeb](/guide/Jsp_TongWeb.md)
   * [2.6 Jetty](/guide/Jsp_Jetty.md)
* [3. Nginx/Tengine自编译说明](/guide/Nginx_README.md)
   * [3.1 安装Nginx\/Tengine防护模块](/guide/Nginx_inst.md)
   * [3.2 卸载Nginx\/Tengine防护模块](/guide/Nginx_uninst.md)
   * [3.3 FAQ](/guide/Nginx_FAQ.md)
* [Linux支持内核版本](/guide/Ker_README.md)
   * [CentOS\/RedHat Linux](/guide/Ker_CentOS.md)
   * [Ubuntu](/guide/Ker_Ubuntu.md)
   * [Suse Linux](/guide/Ker_Suse.md)

## 操作手册
* [1. “添加服务器”操作说明](f01.md)
* [2. “删除服务器”操作说明](f02.md)
* [3. “PC端远程登录”操作说明](f03.md)
* [4. “服务器和Web服务重启”功能操作](f04.md)
* [5. “实时监控”功能说明](f05.md)
* [6. “一键巡检”功能说明](f06.md)
* [7. “网站漏洞防护”功能说明](f0700.md)
  * [7.1 “SQL防注入”功能说明](f0701.md)
  * [7.2 “Web服务器溢出攻击防护”功能说明](f0702.md)
  * [7.3 “文件名解析漏洞防护”功能说明](f0703.md)
  * [7.4 “禁止浏览畸形文件”功能说明](f0704.md)
  * [7.5 “仅允许下列请求类型”功能说明](f0705.md)
  * [7.6 “禁止下载特定类型文件”功能说明](f0706.md)
  * [7.7 “网页浏览实时防护”功能说明](f0707.md)
  * [7.8 “其它设置”说明](f0708.md)
* [8. “网站后台防护”功能设置](f08.md)
* [9. “抗CC攻击”功能设置](f09.md)
* [10. “敏感词过滤”功能设置](f10.md)
* [11. “网站防盗链”功能设置](f11.md)
* [12. "防多线程下载"功能说明](f12.md)
* [13. “HTTP响应内容保护”功能设置](f13.md)
* [14. "HTTP请求头防护"功能说明](f14.md)
* [15. “自定义CDN”功能说明](f15.md)
* [16. “高级防护”功能说明](f16.md)
* [17. “登录防护”功能说明](f17.md)
* [18. “防暴力破解”功能说明](f18.md)
* [19. “文件上传防护”功能设置](f19.md)
* [20. “文件防篡改”功能设置](f20.md)
* [21. “服务器优化”功能设置](f21.md)
* [22. “服务器漏洞修复”功能说明](f22.md)
* [23. “IP黑白名单”功能说明](f23.md)
* [24. “防端口扫描”功能防护](f24.md)
* [25. “系统资源监控”功能说明](f25.md)
* [26. “网站性能监控”功能说明](f26.md)
* [27. “备份与还原”功能设置](f27.md)
* [28. “边界管理”功能说明](f28.md)
* [29. “事件管理”功能说明](f29.md)
* [30. “子账户管理”功能说明](f30.md)

## 常见问题

* [1. 云锁支持的操作系统和Web中间件](faq/q01.md)
* [2. 云锁Linux版本支持的面板](faq/q02.md)
* [3. 云锁收费吗？](faq/q03.md)
* [4. 什么是云锁的服务端和客户端？](faq/q04.md)
* [5. 安装云锁时被杀毒软件误报的问题](faq/q05.md)
* [6. 云锁会否拦截蜘蛛和CDN？](faq/q06.md)
* [7. PC端提示“服务器端连接失败”可能导致的原因](faq/q07.md)
* [8. CC基本设置的含义](faq/q08.md)
* [9. 云锁安装失败，无法再次安装或卸载失败时的解决方法](faq/q09.md)
* [10. 云锁Windows服务器端手工卸载的方法](faq/q10.md)
* [11. 云锁升级相关的问题](faq/q11.md)
* [12. 云锁安装后会影响服务器、网站性能吗？](faq/q12.md)
* [13. VPS共享IP用户登录失败的问题](faq/q13.md)
* [14. 云锁PC端关闭后，服务器端还会继续运行吗？](faq/q14.md)
* [15. 云锁支持虚拟空间吗？](faq/q15.md)
* [16. 云锁可以管理多个服务器吗？](faq/q16.md)
* [17. PC端提示“请求被过滤”的问题](faq/q17.md)
* [18. PC端提示“命令被撤销”的问题](faq/q18.md)
* [19. PC端提示“通道选择器没有找到指定通道”的问题](faq/q19.md)
* [20. 卸载云锁网站无法访问的问题](faq/q20.md)
* [21. 云锁安装后部分功能未生效的问题](faq/q21.md)
* [22. “敏感词过滤”出现不生效的问题](faq/q22.md)
* [23. WDCP卸载云锁后，后台登录失败的问题](faq/q23.md)
* [24. 云锁忘记九宫格密码怎么办？](faq/q24.md)
* [25. Linux安装云锁提示"Detected SElinux opening,close and then  install"的问题](faq/q25.md)
* [26. 将云锁的5555端口添加到防火墙的方法](faq/q26.md)
* [27. 修改Linux服务器端的端口号的方法](faq/q27.md)
* [28. 网站性能监控下为什么多了其它的域名？](faq/q28.md)
* [29. Linux密钥方式怎样登录云锁的PC端](faq/q29.md)
* [30. Linux驱动未加载的问题](faq/q30.md)
* [31. CC攻击设置高级首次访问验证通过后，以后访问还需要输入验证吗？](faq/q31.md)
* [32.  安装Linux版本时，停在“extract compression package”无法继续安装的问题](faq/q32.md)
* [33. 云锁Linux版本Nginx防护插件安装失败的问题](faq/q33.md)
* [34. 云锁开启“抗CC攻击”后，网站访问一直跳转的问题](faq/q34.md)
* [35. PC端显示服务器离线的原因及解决办法](faq/q35.md)
* [36. 页面提示“您所提交的请求含有不合法参数”的问题](faq/q36.md)
* [37. 云锁安装后为什么功能不全？](faq/q37.md)
* [38. 为什么云中心的风险评分与巡检的分数不一致？](faq/q38.md)
* [39. 忘记卸载密码怎么办？](faq/q39.md)