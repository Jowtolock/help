####  云锁忘记九宫格密码怎么办？
**Windows**

方法一：

① 连接到服务器端，关闭服务端防护功能

②  将云锁目录下\\...\YunSuo\YunsuoAgent\config\other\yunsuo_config_other.xml文件里的<client_auth_type>1</client_auth_type>的1改为0
![](/assets/q_24_1.png) 
方法二：
卸载服务器端重新安装

**Linux**

方法一：

① ssh或者本地连接到服务器端

② export LD_LIBRARY_PATH=/usr/local/yunsuo_agent/

③ /usr/local/yunsuo_agent/uninstall_driver

④ vim /usr/local/yunsuo_agent/config/other/yunsuo_config_other.xml
将文件内的<client_auth_type>1</client_auth_type>的1改为0，改完后保存退出
![](/assets/q_24_2.png) 
⑤ service yunsuo restart

方法二：

卸载服务器端重新安装

`/usr/local/yunsu_agent/uninstall`
