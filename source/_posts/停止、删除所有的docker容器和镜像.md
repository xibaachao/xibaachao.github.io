---
categories: 
- 服务器
tags:
- 服务器
---
#### docker停止和删除所有的容器和镜像

#### 停止所有的容器

```
 docker stop $(docker ps -aq) 
```

#### 删除所有的容器

```
docker rm $(docker ps -aq)
```

#### 删除所有的镜像

```
docker rmi $(docker images -q)
```

