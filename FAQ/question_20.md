#### 卸载云锁网站无法访问的问题

卸载云锁后遇到网站打不开问题，在IIS6上请检查IIS 筛选器、IIS通配符应用程序映射以及Web服务扩展这3个地方是否存在云锁插件。

ISAPI筛选器
![IIS筛选器](/assets/q_20_1.png)

IIS通配符应用程序映射
![IIS通配符应用程序映射](/assets/q_20_2.png)

Web服务扩展
![Web服务扩展](/assets/q_20_3.png)

在IIS7和IIS8上请检查IIS模块里是否含有云锁插件

IIS模块
![IIS模块](/assets/q_20_4.png)

在Apache上检查配置文件httpd.conf是否还有云锁插件配置信息
![httpd.conf](/assets/q_20_5.png)

如果存在则删除这些插件重启IIS或Apache服务即可。