---
categories: 
- 服务器
tags:
- 软件使用
---
#### samba 配置以及使用

> yum install samba 安装samba服务器

- 配置文件（ vim /etc/samba/smb.conf）

```bash
[global]
        workgroup = MYGROUP
        server string = Samba Server Version %v
        security = user
        passdb backend = tdbsam
        load printers = yes
        cups options = raw
[homes]
        comment = Home Directories
        browseable = no
        writable = yes
[printers]
        comment = All Printers
        path = /var/spool/samba
        browseable = no
        guest ok = no
        writable = no
        printable = yes
```

修改：

- workgroup=MYGROUP 修改成 WORKGROUP

- 添加代码

  - ```bash
    [share]
            comment = share all
            path = /tmp/samba
            browseable = yes
            public = yes
            writable = yes
    ```

    > path 表示目录

设置访问账号密码

```
smbpasswd -a  用户    // 设置访问密码
```

开机启动

> chkconfig smb on 
>
> systemctl start smb.service





> 注意事项
>
> 1、如果访问不到，请先关闭防火墙。
>
> 2、通过  vim /etc/sysconfig/selinux 把 SELINUX=enforcing  修改为SELINUX= disable 退出保存