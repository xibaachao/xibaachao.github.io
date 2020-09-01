---
categories: 
- 编程开发
tags:
- PHP

---

word 转pdf  LibreOffice 转pdf

<!--more-->

### 1、安装环境

```bash
yum install libreoffice
yum install libreoffice-headless
```

### 2、执行转换命令

```bash
soffice --headless --convert-to pdf {文档路径} --outdir {导出目录路径}
```

注意：如果中文会出现乱码问题，这个时候需要把Windows下的字体C:\Windows\Fonts下的常用字体，即simsun.ttc等复制到usr/share/fonts目录下。

### 3、在程序中执行命令

```php
$retval = 1;
// exec() might be disabled
$cmd = 'export HOME=/tmp/ && /usr/bin/libreoffice --headless --convert-to pdf 1.doc --outdir ./';
if (function_exists('exec')){
    @exec($cmd, $output, $retval);
}
// Did it work?
if ($retval > 0){
    exit('process_failed');
}
echo 'success';
```