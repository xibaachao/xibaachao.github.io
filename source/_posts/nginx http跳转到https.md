---
categories: 
- 服务器
tags:
- nginx

---

#### nginx http 跳转到https

```nginx
server {
 listen 80;
 server_name www.0305.ink;
  location / {
    root /usr/share/nginx/www.0305.ink/;
    index index.php index.html;
    return 301 https://$server_name$request_uri; 
 }
 location ~ \.php$ {
    fastcgi_pass php7:9000;
    fastcgi_index index.php;
    fastcgi_param SCRIPT_FILENAME /var/www/www.0305.ink/$fastcgi_script_name;
    include fastcgi_params;
 }
}
```

