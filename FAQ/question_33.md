#### Nginx安装云锁Linux版本防护插件失败的问题 

1.“checking nginx”提示“Not Found”
  ![](/assets/q_33_1.png)

产生该提示的原因主要有2个，一种是安装云锁Linux版本时Nginx未正常运行；另一种是Nginx加载了第三方模块。通过命令“nginx -V”查看是否有加载第三方模块。

2.“checking nginx”提示“Configure nginx failed,May this version is not supported”

![](/assets/q_33_2.png)

产生该提示原因也有2个，一种为Nginx进行过二次开发；另一种是网络不稳定，导致Nginx防护插件下载失败，可以通过查看/usr/local/yunsuo_agent/runlog/update.log查看。

如果加载了第三方模块或者进行过二次编译，可以通过自编译带有yunsuo的模块来支持这2种情况。

3.“checking nginx”提示“ls: cannot access…”

![](/assets/q_33_3.png)

因为当前系统Nginx本身异常或Nginx进程异常，重新调试或者重新安装Nginx后再次安装云锁。