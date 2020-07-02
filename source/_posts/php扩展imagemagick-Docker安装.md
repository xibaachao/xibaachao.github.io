---
categories: 
- 服务器
tags:
- PHP
---
#### 创建PHP DOCKER容器

进入php容器后

```html
apt-get update 
apt-get install -y libmagickwand-6.q16-dev --no-install-recommends 
rm -rf /var/lib/apt/lists/*
```

安装插件所需要的环境

```html
pecl install imagick-3.4.3 
docker-php-ext-enable imagick
```

安装插件（目前最高版本为3.4.4）