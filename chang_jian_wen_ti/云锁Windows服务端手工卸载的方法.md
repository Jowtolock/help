#### 云锁Windows服务端手工卸载的方法

1. cmd下执行以下命令：
 <pre><code>sc stop yunsuoagent
 sc delete yunsuoagent
 sc stop yunsuodaemon
 sc delete yunsuodaemon
 sc delete resguard
 sc delete resguard2
 sc delete secmodel</code></pre>
2. 删除云锁安装目录

3. 重启服务器