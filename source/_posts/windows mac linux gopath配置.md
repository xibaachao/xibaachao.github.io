---
categories: 
- 编程开发
tags:
- GO

---

#### MAC GOPATH 配置

1、先创建一个go的工作目录 比如：/Users/你的用户名/app/go

2、编辑.bash_profile vim ~/.bash_profile

3、在.bash_profile中新增

```
export GOPATH=/Users/你的用户名/app/go 
```

4、保存

5、在/Users/你的用户名/app/go 下分别建立 bin、src、pkg文件夹

#### windows GOPATH配置

1、先创建一个go的工作目录，比如D:\app\go

2、右键计算机属性->系统高级设置->环境变量

![](/images/2020/5.png)

3、添加或者修改GOPATH 路径如上图

4、确定

5、在go工作目录下分别建立 bin、src、pkg文件夹

#### LINUX GOPATH配置

1、先创建一个go的工作目录，比如/home/app/go

2、编辑profile vim /etc/profile

3、配置go环境

```
export GOROOT=/usr/local/go  #设置为go安装的路径，有些安装包会自动设置默认的goroot
export GOPATH=$HOME/gocode   #默认安装包的路径
export PATH=$PATH:$GOROOT/bin:$GOPATH/bin
```

4、生效profile (命令：source /etc/profile)

5、在go工作目录下分别建立 bin、src、pkg文件夹