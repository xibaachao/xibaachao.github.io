---
categories: 
- 服务器
tags:
- linux

---

关于linux解压缩命令！这里推荐使用`zip`和 `unzip`

<!--more-->

##### zip 命令： 

zip xxx.zip xxx.txt 

它会将 xxx.txt 文件压缩为 xxx.zip ，当然也可以指定压缩包的目录，例如 /root/test.zip 

#### unzip 

unzip test.zip 

它会默认将文件解压到当前目录，如果要解压到指定目录，可以加上 -d 选项 

unzip test.zip -d /home/

- 注意如果发现unzip找不到这个命令，就执行 ` yum install -y unzip zip`

