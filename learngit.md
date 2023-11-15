# Git学习笔记

## Git的安装

git安装之要进行注册。注册的命令是：

```
git config --global user.name "jinfeng" `
git config --global user.email "jinfeng.dalian@gmail.com"
```

上面的两个命令本质上是在Gitr配置文件(~/.gitconfig)添下如下配置：

```
[user]
	name = JinFeng
	email = jinfeng.dalian@gmail.com
```

注意：`git config`命令的`--global`参数，表示在这台器上所有的Git仓库都会使用这个配置。


##  创建版本库

版本库（repository）可以理解成目录，目录里所有的文件都可以被git管理。
在需要创建版本库的目录下，输入以下命令：`git init`。返回提示：
``Initialized empty Git repository in /Users/jinfeng/Documents/learngit/.git/``

