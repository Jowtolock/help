## 云锁一直提示“正在升级”的问题

1.  查看/usr/local/yunsuo_agent/目录，如果没有update文件则
 <br>\# killall YSUpdate
2.  如果有update文件则
 <br>\# export LD_LIBRARY_PATH=/usr/local/yunsuo_agent/
 <br>\# /usr/local/yunsuo_agent/uninstall_driver
 <br>\# rm -rf /usr/local/yunsuo_agent/update
 <br>\# ps -ef | grep YSUpdate
 <br>\# kilalll YSUpdate