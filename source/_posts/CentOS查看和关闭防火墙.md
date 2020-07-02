---
categories: 
- 服务器
tags:
- 服务器
---
#### CentOS7查看和关闭防火墙

- 查看防火墙

```bash
firewall-cmd --state
```



- 停止firewall

```
systemctl stop firewalld.service
```



- 禁止firewall开机启动

```
systemctl disable firewalld.service 
```

- 关闭selinux 

```
进入到/etc/selinux/config文件
vi /etc/selinux/config
将SELINUX=enforcing改为SELINUX=disabled
```

