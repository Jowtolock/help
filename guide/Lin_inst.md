#### Linux服务器端安装说明
##### 安装云锁
1.下载云锁安装包。
      
    x86：wget http://download.yunsuo.com.cn/v3/yunsuo_agent_32bit.tar.gz
    x64：wget http://download.yunsuo.com.cn/v3/yunsuo_agent_64bit.tar.gz
2.检查并关闭selinux，否则无法安装云锁；如已关闭则忽略此步骤。

    检查selinux状态
    # getenforce    ##如果显示参数为enabled即为开启状态
    关闭selinux
    修改/etc/sysconfig/selinux文件，将enforcing改为disabled，重启服务器。
    # vim /etc/sysconfig/selinux
![](/assets/Linux_install_1.png)
3.解压文件，得到安装包文件。

    x86：tar zxvf yunsuo_agent_32bit.tar.gz
    x64：tar zxvf yunsuo_agent_64bit.tar.gz
4.执行安装，直到提示“Install Yunsuo Success.”安装完成。
    # cd yunsuo_install/
    # ./install
 ![](/assets/Linux_install_2.png)
5.安装完成后通过[PC端](/PC_inst.md)进行管理。

##### 查看云锁是否运行
    ps -ef | grep yunsuo_agent
![](/assets/Linux_install_3.png)
##### 云锁服务相关命令 
###### 云锁启动/停止/重启/状态
    service yunsuo start/stop/restart/status
    /etc/init.d/yunsuo start/stop/restart/status
##### 卸载云锁
    /usr/local/yunsuo_agent/uninstall