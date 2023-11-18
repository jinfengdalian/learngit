Git学习笔记
====

### Git的安装

git安装之要进行注册。注册的命令是：

```
git config --global user.name "jinfeng" `
git config --global user.email "jinfeng.dalian@gmail.com"
```

上面的两个命令本质上是在Gitr配置文件`~/.gitconfig`添下如下配置：

```
[user]
	name = JinFeng
	email = jinfeng.dalian@gmail.com
```

注意：`git config`命令的`--global`参数，表示在这台器上所有的Git仓库都会使用这个配置。


###  创建版本库

版本库（repository）可以理解成目录，目录里所有的文件都可以被git管理。
在需要创建版本库的目录下，输入以下命令：`git init`。返回提示：

`Initialized empty Git repository in /Users/jinfeng/Documents/learngit/.git/`

#### 把文件添加到仓库

`git add learngit.md`

#### 把文件提交到仓库

`git commit -m "第一次写的markdown格工的Git学习笔记"`

成功返回提示如下:

```
[main (root-commit) 6fcbff6] 第一次写的markdown格工的Git学习笔记
 1 file changed, 28 insertions(+)
 create mode 100644 learngit.md
jinfeng@jinfengdeMac-mini learngit % 
```

`-m "xxx"` 后面输入的是本次提交的说明，引号必须有，不显示。

`add`一次只能添加一个文件，而`commit`一次可以提交多个不同的文件。

### 查看当前git状态

#### 查看当前git的状态

`git --status`

返回

```
On branch main
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   learngit.md
no changes added to commit (use "git add" and/or "git commit -a")
```

#### 查看git更改内容

`git diff learngit.md`

返回

```
diff --git a/learngit.md b/learngit.md
index 86fb1b5..7b69577 100644
--- a/learngit.md
+++ b/learngit.md
@@ -9,7 +9,7 @@ git config --global user.name "jinfeng" `
 git config --global user.email "jinfeng.dalian@gmail.com"
 
-上面的两个命令本质上是在Gitr配置文件(~/.gitconfig)添下如下配置：
+上面的两个命令本质上是在Gitr配置文件`~/.gitconfig`添下如下配置：
 
 [user]
@@ -24,5 +24,26 @@ git config --global user.email "jinfeng.dalian@gmail.com"
 
 版本库（repository）可以理解成目录，目录里所有的文件都可以被git管理。
 在需要创建版本库的目录下，输入以下命令：`git init`。返回提示：
-``Initialized empty Git repository in /Users/jinfeng/Documents/learngit/.git/``
 
+`Initialized empty Git repository in /Users/jinfeng/Documents/learngit/.git/`
+
+- 把文件添加到仓库
+
+`git add learngit.md`
+
+- 把文件提交到仓库
+
+`git commit -m "第一次写的markdown格工的Git学习笔记"`
+
+成功返回提示如下:
+
+```
+[main (root-commit) 6fcbff6] 第一次写的markdown格工的Git学习笔记
+ 1 file changed, 28 insertions(+)
+ create mode 100644 learngit.md
+jinfeng@jinfengdeMac-mini learngit % 
+```
+
+`-m "xxx"` 后面输入的是本次提交的说明，引号必须有，不显示。
+
+`add`一次只能添加一个文件，而`commit`一次可以提交多个不同的文件。
```
`-`号代表删掉的部分，`+`代表添加的部分。

### 版本回退

在回退之前，必须定位。知道要退到哪一步，才能回退。没有坐标和方位是不能讲回退的。

#### 查看历史记录

`git log`

返回

```
commit 8e5dc045243a6a028d67c894b63684c4bd9ad9b4 (HEAD -> main)
Author: JinFeng <jinfeng.dalian@gmail.com>
Date:   Fri Nov 17 22:00:10 2023 +0800

    把一些二级标题改成三级标题

commit 477e404fb1adb6981913ae4356352617a4cd1587
Author: JinFeng <jinfeng.dalian@gmail.com>
Date:   Thu Nov 16 19:49:23 2023 +0800

    添加status，diff的笔记

commit da01e1dd4456aa1676ba37ee1011c6dca288b2e5
Author: JinFeng <jinfeng.dalian@gmail.com>
Date:   Thu Nov 16 19:31:51 2023 +0800

    提交test.md

commit 6fcbff61d62a9d3d73367e094b5127c8fb397097
Author: JinFeng <jinfeng.dalian@gmail.com>
Date:   Wed Nov 15 22:30:40 2023 +0800

    第一次写的markdown格工的Git学习笔记
jinfeng@jinfengdeMac-mini learngit % 
```

其中的`(HEAD -> main)`表示当前位置。其中的`8e5dc045243a6a028d67c894b63684c4bd9ad9b4`是那一次提交的序号，学名版本号。

#### 恢复文件

`git reset --HEAD`

其中HEAD是版本号。版本号不一定写全，写头几位，可能是6位就差不多了。

还有一个功能更强的命令，可以查看已经被删除了的版本号，换句话说是后悔之后又后悔了。

`git reflog`



