---
categories: 
- 编程开发
tags:
- 服务器
---
### nginx 负载均衡配置及介绍

#### 什么是负载均衡

负载均衡说白了就一个反向代理，看下图。

![](/images/2020/2.png)

#### 为什么要使用负载均衡

1、解决高并发压力，提高web应用处理性能

#### 负载均衡模式

> 1、默认模式（轮询）
>
> 2、权重模式
>
> 3、ip_hash
>
> 4、url_hash
>
> 5、第三发

#### 默认模式

```html
http{
	 upstream temp { //格式:upstream 名称
        server 10.10.1.1:80;
        server 10.10.1.2:80;
        server example.com:80; //格式:域名+端口 或者 ip+端口
    }
	server{       
        listen 80;
        location / {
            proxy_pass http://temp;
        }
    }
}
```

注：就是挨个访问，如果某个服务器宕机，那么就会跳过



#### 权重模式

```
http{
    upstream temp {
        server 10.10.1.1:80 weight=3;
        server 10.10.1.2:80 weight=7;
    }
    server{       
        listen 80;
        location / {
            proxy_pass http://temp;
        }
    }
}
```

注：就是指定几率访问，比如weight=7 那么70%的流量就会走这台服务器

#### ip_hash

```html
http{
    upstream temp {
        ip_hash;
        server 10.10.1.1:80;
        server 10.10.1.2:80;
    }
	server{       
        listen 80;
        location / {
            proxy_pass http://temp;
        }
    }
}
```

注：ip_hash 会通过用户的ip定位服务器，比如：用户访问了A服务器，已经登录过了，已存在session。如果不是使用ip_hash那么就有可能会访问到B服务器，那么这个时候的session就会出现问题。当然我这里只是打个比方，一般用了负载均衡session都是要共享的，或者是使用radis来管理session

#### url_hash

```html
http{
    upstream temp {
        hash $request_uri；
        server 10.10.1.1:80;
        server 10.10.1.2:80;
    }
	server{       
        listen 80;
        location / {
            proxy_pass http://temp;
        }
    }
}
```

注：url_hash 会通过用户访问的url定位服务器。此模式需要使用**高版本**nginx，低版本需要自己安装扩展！

#### 第三方（fair）

```html
http{
    upstream temp {
        fair;
        server 10.10.1.1:80;
        server 10.10.1.2:80;
    }
	server{       
        listen 80;
        location / {
            proxy_pass http://temp;
        }
    }
}
```

注：哪台服务器响应快就访问哪台服务器！



#### 其他常用配置说明

```
http{
    upstream temp {
        ip_hash;
        server 10.10.1.1:80 down;//表示这台服务器不参与负载
        server 10.10.1.3:80 backup;//表示这台服务器在其他服务器都宕机或者忙的时候在参与负载（不包含 down）
        server 10.10.1.3:80 max_fails=1;//表示最大请求失败数，比如访问失败一次就跳过该服务器
        server 10.10.1.4:80 fail_timeout=5s;//发生错误暂停5秒
        server 10.10.1.5:80
    }
	server{       
        listen 80;
        location / {
            proxy_pass http://temp;
        }
    }
}
```



