---
categories: 
- 编程开发
tags:
- PHP

---

php 删除文件操作

<!--more-->

### 只删除文件夹包含的文件,不删除文件夹

```php
public function deldir($dir) {
	//先删除目录下的文件：
	$dh = opendir($dir);
	while ($file = readdir($dh)) {
		if($file != "." && $file!="..") {
		$fullpath = $dir."/".$file;
		if(!is_dir($fullpath)) {
			unlink($fullpath);
		} else {
			deldir($fullpath);
		}
		}
	}
	closedir($dh);
	
}
```

### 删除文件夹及文件夹下所有的文件

```php
public function deldir($dir) {
	//先删除目录下的文件：
	$dh = opendir($dir);
	while ($file = readdir($dh)) {
		if($file != "." && $file!="..") {
		$fullpath = $dir."/".$file;
		if(!is_dir($fullpath)) {
			unlink($fullpath);
		} else {
			deldir($fullpath);
		}
		}
	}
	closedir($dh);
	
	//删除当前文件夹：
	if(rmdir($dir)) {
		return true;
	} else {
		return false;
	}
}
```

### 创建文件夹并指定权限和编码

```php
if (!is_dir($dir)){                                 //如果目录不存在
	mkdir(iconv("UTF-8", "GBK", $dir),0777,true);   //创建目录,777权限,GBK编码格式
}
```



