1. 什么情况下需要自己编译云锁的nginx模块？

 1） 当您的nginx使用了第三方或者自己开发的模块的时候，需要编译云锁的nginx模块。您可以通过nginx -V命令查看输出的信息里是否包含了--add-module=的字样 (例如：--add-module=../ngx_cache_purge-1.3说明使用了ngx_cache_purge-1.3第三方模块)

 2） 当使用tengine的时候，需要编译云锁的nginx模块 

 3） 当前使用的nginx版本比匀速适配的nginx版本高的时候，需要自己编译云锁的nginx模块
2. 卸载云锁后nginx需要重新编译吗？

 不需要，云锁的nginx模块会判断防护模块是否安装，如果不安装则不生效。当然您也可以替换回之前的nginx
3. 编译时可能出现的几种错误解决方法

```
 1）遇如下错误信息 ： cc1: all warnings being treated as errors， 编译器把警告信息作为错误处理了
    解决： 修改 objs/Makefile
    把CFLAGS = -pipe -O -W -Wall -Wpointer-arith -Wno-unused-parameter -Werror -g修改为：CFLAGS = -pipe -O -W -Wall -Wpointer-arith -Wno-unused-parameter -g即去掉-Werror选项
    重新 make， 注意是重新make 而不是重新 ./configure
 
 2) 遇如下错误信息：undefined reference to `dlclose'，由于编译器版本过高，需要在链接时，加入-ldl 选项
    解决： 修改 objs/Makefile
    搜索 -lpthread，定位到该行结束，加入 -ldl
    形如 -lpthread -lcrypt 修改为 -lpthread -lcrypt -ldl
    重新 make，注意是重新make而不是重新./configure 
```