---
categories: 
- 服务器
tags:
- 服务器

---

yum install docker -y & systemctl start docker & systemctl enable docker

<!--more-->

- docker 一键安装脚本

  ```shell
  curl -fsSL https://get.docker.com -o get-docker.sh
  sh get-docker.sh
  ```

- 开启服务

  ```shell
  service docker start 或者 systemctl start docker
  ```

- 设置开机启动

  ```shell
  systemctl enable docker
  ```

  