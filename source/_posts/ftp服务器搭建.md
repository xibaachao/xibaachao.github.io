---
categories: 
- 服务器
tags:
- 服务器

---

yum install vsftpd -y

<!--more-->

- 安装服务

  ```shell
  yum install vsftpd -y //安装软件
  systemctl restart vsftpd.service //重启软件
  systemctl enable vsftpd.service
  ```

- 创建用户

  ```shell
  useradd ftpuser //创建用户
  echo "Password" | passwd ftpuser --stdin //设置密码
  usermod -s /sbin/nologin ftpuser //禁止登陆
  
  ```

- 设置目录

  ```
  chmod 777 -R /home/www/xxxx.com //设置权限
  usermod -d /home/www/xxxx.com ftpuser //设置主目录
  ```

- 常见问题

  `530 Login incorrect`

  1、查看/etc/ftpusers ，确保账号没有在这个文件内。
   2、修改/etc/pam.d/vsftpd
   将`auth required pam_shells.so`修改为->`auth required pam_nologin.so` 即可
   3、重启vsftpd