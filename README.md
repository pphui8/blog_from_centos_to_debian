## 从 centos 转用 debian 服务器的历程
> centos8.2 -> debian10
> 腾讯云 -> azure

一些小问题
1. azure的服务器默认不支持ping测试ip连通性
2. git clone时显示没有权限链接失败。解决：使用tcp的那个链接进行clone
3. 使用apt-get作为包管理器而不是yum
6. nginx 下载后需要 root 权限运行，即使用 sudo nginx 而不是 nginx 来运行。

### 用户权限问题
azure购买时设置了公钥方式作为ssh链接认证，可以设为密码方式，但不知道为啥root用户的密码在哪设置找不到。使用 ```sudo su``` 来获取 root 用户权限


### 时区问题
这次买的服务器默认使用世界时间，使用 timedatectl 来修改时区。
查看当前时区：timedatectl
列出可用地区：timedatectl list-timezones
设置时区：sudo timedatectl set-timezone your_time_zone
