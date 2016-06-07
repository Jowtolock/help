## 云锁一直提示“正在升级”的问题

1.  ls /usr/local/yunsuo_agent/目录，如果没有update文件则

# killall YSUpdate

1.  如果有update文件则

# export LD_LIBRARY_PATH=/usr/local/yunsuo_agent/

# /usr/local/yunsuo_agent/uninstall_driver

# rm -rf /usr/local/yunsuo_agent/update

# ps -ef | grep YSUpdate

# kilalll YSUpdate