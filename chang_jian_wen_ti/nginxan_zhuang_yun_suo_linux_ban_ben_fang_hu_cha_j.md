## Nginx安装云锁Linux版本防护插件失败的问题 {#nginx-linux}

*   1.  “checking nginx”提示“Not Found”

![http://bbs.yunsuo.com.cn/data/attachment/forum/201604/08/150950t7c7y93a5ktvi5ii.jpg](assets/httpbbsyunsuocomcndataattac.jpeg)

一般造成这个提示的原因主要有2个，一种是安装云锁Linux版本时Nginx未正常运行；另一种是Nginx加载了第三方模块。通过命令“# nginx -V”查看是否有加载第三方模块。

*   1.  “checking nginx”提示“Configure nginx failed,May this version is not supported”

![http://bbs.yunsuo.com.cn/data/attachment/forum/201604/08/150956x7s8so8d33v7x4of.png](assets/httpbbsyunsuocomcndataattac.png)

一般造成这个提示原因也有2个，一种为Nginx进行过二次开发；另一种是网络不稳定，导致Nginx防护插件下载失败，可以通过查看/usr/local/yunsuo_agent/runlog/update.log查看。

如果加载了第三方模块或者进行过二次编译，可以通过自编译带有yunsuo的模块来支持这2种情况。自编译教程：http://bbs.yunsuo.com.cn/forum.p ... 2679&extra=page%3D1

*   1.  “checking nginx”提示“ls: cannot access…”

通常因为当前系统Nginx本身异常或Nginx进程异常，重新调试或者重新安装Nginx后再次安装云锁。