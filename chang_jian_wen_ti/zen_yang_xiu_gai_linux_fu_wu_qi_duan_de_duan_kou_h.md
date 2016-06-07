## 怎样修改Linux服务器端的端口号？

云锁的根目录/usr/local/yunsuo_agent/下有可执行脚本yunsuo_smart_tool.sh，执行该脚本即可修改Linux服务器端的端口号。通过参数h可以知道具体的修改方法。

# ./yunsuo_smart_tool.sh –h #查看工具yunsuo_smart_tool.sh帮助

# ./yunsuo_smart_tool.sh -u cloud_name -p cloud_passwd #添加云中心账户名和密码

# ./yunsuo_smart_tool.sh -l port #更新端口号

# ./yunsuo_smart_tool.sh -i port #添加端口号

# ./yunsuo_smart_tool.sh -d port #删除端口号

# ./yunsuo_smart_tool.sh -P proxy_server_ip #更新代理IP