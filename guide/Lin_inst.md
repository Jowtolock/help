#### Linux服务器端安装说明
检查并关闭selinux，否则无法安装云锁；如已关闭则忽略此步骤。

![](/assets/Linux_install_0.png)

1) 检查selinux状态
    
    # getenforce ##如果显示参数为disabled则为成功关闭
    
2） 关闭selinux。修改/etc/sysconfig/selinux文件，将enforcing改为disabled，重启服务器。如已经是disabled则直接重启服务器。
    
    # vim /etc/sysconfig/selinux

![](/assets/Linux_install_1.png)

>#### 安装云锁

**注意：**如曾经下载过云锁安装包，则将旧的云锁安装包及安装目录删除**（rm -rf yunsuo_*）**后再安装。

##### 快速安装

x86：wget http://download.yunsuo.com.cn/v3/yunsuo_agent_32bit.tar.gz && tar xvzf yunsuo_agent_32bit.tar.gz && chmod +x yunsuo_install/install && yunsuo_install/install

x64：wget http://download.yunsuo.com.cn/v3/yunsuo_agent_64bit.tar.gz && tar xvzf yunsuo_agent_64bit.tar.gz && chmod +x yunsuo_install/install && yunsuo_install/install

##### 分步安装

1. 下载云锁安装包。
      
    x86：wget http://download.yunsuo.com.cn/v3/yunsuo_agent_32bit.tar.gz
    x64：wget http://download.yunsuo.com.cn/v3/yunsuo_agent_64bit.tar.gz

2. 解压文件，得到安装包文件。

    x86：tar zxvf yunsuo_agent_32bit.tar.gz
    x64：tar zxvf yunsuo_agent_64bit.tar.gz
    
3. 给云锁安装文件赋予可执行权限。

    chmod +x yunsuo_install/install

4. 执行安装，直到提示“Install Yunsuo Success.”安装完成。
    
    yunsuo_install/install
 
    ![](/assets/Linux_install_2.png)
 
5. 添加服务器到云中心。

    /usr/local/yunsuo_agent/yunsuo_smart_tool.sh -u cloud_name -p cloud_passwd
    说明：cloud_name：云中心账户名；cloud_passwd：云中心登录密码

    ![](/assets/f0105.png)

6. 安装完成后通过[PC端](http://help.yunsuo.com.cn/guide/PC_inst.html)进行管理。

>#### 查看云锁是否运行
   
     ps -ef | grep yunsuo_agent

![](/assets/Linux_install_3.png)
>#### 云锁服务相关命令 

##### 云锁启动/停止/重启/状态

    service yunsuo start/stop/restart/status
    /etc/init.d/yunsuo start/stop/restart/status

>#### 卸载云锁

    /usr/local/yunsuo_agent/uninstall