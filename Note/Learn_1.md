# 查看git的用户名和邮箱
用户名和邮箱的作用：  
   1.相当于身份标识，是本地Git客户端的一个变量，不会随着git库而改变。  
   2.每次Commit都会记录用户名和邮箱，github的共享量也是跟邮箱有关联的。  

   注意：用github desktop的话，用clone下来的仓库，在Github Desktop中的设置可以该更用户名和邮箱。再在git中可以看到用户名和邮箱。

- 查看用户名的命令：
```
$ git config user.name
$ git config user.email
```
- 修改自己的用户名和邮箱地址：
```
$ git config --global user.name "xxx"
$ git config --global user.email "xxx"
```
---

# 新建代码库
- 在当前目录下新建一个git代码仓库
```
$ git init
```
注意：在github Desktop中Clone的仓库不需要使用该命令，因为用github的中clone下来的本身就是一个仓库，你可以利用ls -all看到文件夹中是包含一个.git文件夹的。

- 新建一个目录，并将其初始化为git代码库
```
$ git init [project-name]
```
这个会直接建立一个文件夹，相当于先mkdir [project-nme]，然后进入该文件夹git init。

- 下载一个项目和它的整个代码历史

```
$ git clone [url]
```
这个clone下来也是带了仓库的，不需要再git init。

---
# 配置
Git的配置文件是.gitconfgi，它可以在用户主目录下配置（全局配置），也可以在当前项目目录下（项目配置）。
- 显示配置
```
$ git config --list
```
- 编辑配置
```
$ git config -e [--global]
```
- 设置提交代码的用户信息
```
$ git config [--global] user.name '[name]'
$ git config [--global] user.email '[emai address]'
```

---
# 增加/删除文件
- 添加制定文件到暂存区
```
$ git add [file1] [file2] ...
```

- 添加指定目录到暂存区，包括子目录
```
$ git add [dir]
```

- 添加当前目录的所有文件到暂存区
```
$ git add .
```

- 添加每个变化前，都会要求确认，对于同一个文件的多处变化，可以实现分次提交
```
$ git add -p
```

- 删除工作区文件，并且将这次删除放入暂存区
```
$ git rm [file1] [file2] ...
```

- 停止追踪指定文件，但该文件会保留在工作区
```
$ git rm --cached [file]
```

- 改名文件，并且将这个改名放入暂存区
```
$ git mv [file-original] [file-renamed]
```

---
# 代码提交
- 提交暂存区到仓库区
```
$ git commit -m [message]
```

- 提交暂存区的指定文件到仓库区
```
$ git commit [file1] [file2] ... -m [message]
```

- 提交工作区自上次commit之后的变化，直接到仓库区
```
$ git commit -a
```

- 提交时显示所有diff信息
```
$ git commit -v
```

- 使用一次新的commit，替代上一次提交，如果代码没有任何新变化，则用来改写上一次commit的提交信息
```
$ git commit --amend -m [message]
```

- 重做上一次commit，并包括指定文件的新变化
```
$ git commit --amend [file1] [file2] ...
```