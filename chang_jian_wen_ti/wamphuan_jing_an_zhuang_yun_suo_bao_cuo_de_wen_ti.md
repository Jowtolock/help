## Wamp环境安装云锁报错的问题 {#wamp}

使用wamp的用户在安装云锁后会弹出一个告警框，可能会导致导致wamp启动失败。

产生这个问题的主要原因是wamp使用的非官方php程序，而这个程序的库是用vc6编译的；云锁使用的库是使用vc9编译的，所以导致wamp程序冲突。遇到这个问题可以临时将php.ini中的extension=php_secmod.dll这句注释掉即可。