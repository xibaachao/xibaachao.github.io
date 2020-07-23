---
categories: 
- 编程开发
tags:
- 服务器
---

#### 初始化git工作目录
```
git init //初始化目录
git clone <url> //克隆远程
git clone -b <branch_name> <url> //克隆远程分支
```

#### 追踪文件

```
git add . //追踪所有改动过的问题件
git add * //追踪所有改动过的问题件
git add <file> //追踪指定文件
```


#### 提交所有更新过的文件
```
git commit -m "messages"
```


#### 撤销操作
```//
git reset --hard HEAD //撤销工作目录中未提交的文件
git checkout HEAD <file> //撤销指定未修改的内容
git revert HEAD //撤销指定的commit 
git revert //撤销上一次commit
```

#### 分支

```
git branch //显示本地分支
git branch -a //显示所有分支名称（包含本地和远程）
git checkout <bracnch/tag> //切换到指定分支或者标签
git checkout -b <branch> //创建分支并切换分支
git checkout -b <new-branch> origin <branch> //获取远程分支并创建本地分支
git branch <new-branch> //创建分支
git branch -d <branch> //删除分支
git remote set-url origin https://~.git //修改远程分支
```

#### 标签

```
git tag //显示本地标签
git tag -a <tagname> -m "message" //创建标签
git tag -d <tagname> //删除标签
```

#### 合并

```
git merge <branch> //合并分支
git rebase -i HEAD~4 //合并最近4次commit
```

#### 提交

```
git push //提交当前分支
git push origin <branch> //提交指点远程分支
```

#### 下载

```
git pull
```





