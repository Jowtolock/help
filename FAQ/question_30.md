#### Linux驱动未加载的问题

查看云锁目录下是否有云锁驱动文件resguard\_linux.ko、secmodel\_linux.ko、yunsuo\_ipfilter.ko；

```
 # ls /usr/local/yunsuo_agent    # 查看云锁安装文件
```

如果没有上述驱动文件则查看操作系统的内核版本是否为云锁支持的版本；如果不支持则为正常。如果支持则可能是下载驱动失败，再次下载驱动并重启云锁服务加载驱动。

```
  # uname –a    # 查看Linux系统内核版本号
  # /usr/local/yunsuo_agent/YSUpdate 1    # 下载云锁驱动
  # service yunsuo restart    # 重启云锁服务
```

