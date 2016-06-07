## Linux驱动未加载的问题 {#linux}

查看云锁目录下是否有云锁驱动文件resguard_linux.ko、secmodel_linux.ko、yunsuo_ipfilter.ko；

# ls /usr/local/yunsuo_agent _# 查看云锁安装文件_

1.  如果没有上述驱动文件则查看操作系统的内核版本是否为云锁支持的版本；如果不支持则为正常。如果支持则可能是下载驱动失败，再次下载驱动并重启云锁服务加载驱动。

# uname –a _# 查看Linux系统内核版本号_

# /usr/local/yunsuo_agent/YSUpdate 1 _# 下载云锁驱动_

# service yunsuo restart _# 重启云锁服务_

1.  如有上述驱动文件则查看template目录下是有文件，如没有文件则为asve规则文件下载失败，重新下载该文件并加，成功加载后重启云锁服务加载驱动。

# ls /usr/local/yunsuo_agent/template _# 查看asve规则文件是否下载_

# /usr/local/yunsuo_agent/YSUpate 3 _#_ _下载asve规则文件_

# /usr/local/yunsuo_agent/default_rule_install.sh _#_ _加载asve规则文件_

# service yunsuo restart _# 重启云锁服务_