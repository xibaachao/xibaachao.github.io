---
categories: 
- 服务器
tags:
- 服务器
---
#### 获取brew install文件

```
https://raw.githubusercontent.com/Homebrew/install/master/install
```

#### 编辑install文件

将

```bash
BREW_REPO = “https://github.com/Homebrew/brew“.freeze
CORE_TAP_REPO = “https://github.com/Homebrew/homebrew-core“.freeze
```

替换成

```bash
BREW_REPO = “https://mirrors.ustc.edu.cn/brew.git “.freeze
CORE_TAP_REPO = “https://mirrors.ustc.edu.cn/homebrew-core.git“.freeze
```



#### 执行脚本





