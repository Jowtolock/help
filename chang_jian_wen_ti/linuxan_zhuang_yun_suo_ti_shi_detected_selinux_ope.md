## Linux安装云锁提示Detected SElinux opening,close and then install的问题

![http://bbs.yunsuo.com.cn/data/attachment/forum/201503/28/180123yz2smm24991sixcv.png](assets/httpbbsyunsuocomcndataattac.png)

提示该问题是因为系统的Selinux未关闭，Selinux开启的状况下会影响云锁的安装与使用，所以需要关闭Selinux才可以安装。

**关闭SELinux的方法：**

方法一：vim /etc/selinux/config文件中的SELINUX=“enforcing”改为disabled ，按住shift键+：wq退出，然后（reboot）重启。

![http://bbs.yunsuo.com.cn/data/attachment/forum/201502/09/104738p0u11nl09khhb7zp.png](assets/httpbbsyunsuocomcndataattac.png)

方法二：在lilo或者grub的启动参数中增加：selinux=0,也可以关闭selinux

vim /boot/grub/grub.conf，将selinux=1改为selinux=0。保存退出后reboot重启系统。

重启后查看selinux状态：

getenforce

Disabled