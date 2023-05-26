### git基础知识

 Git 有三种状态: **已提交（committed）、已修改（modified） 和 已暂存（staged）。**

1. 已修改表示修改了文件，但还没保存到数据库中。

2. 已暂存表示对一个已修改文件的当前版本做了标记，使之包含在下次提交的快照中。

3. 已提交表示数据已经安全地保存在本地数据库中。

这会让我们的 Git 项目拥有三个阶段：**工作区**、**暂存区**以及 **Git 目录**。

基本的 Git 工作流程：

1. 在工作区中修改文件。

2. 将你想要下次提交的更改选择性地暂存，这样只会将更改的部分添加到暂存区。

3. 提交更新，找到暂存区的文件，将快照永久性存储到 Git 目录。


请记住，你工作目录下的每一个文件都不外乎这两种状态：**已跟踪** 或 **未跟踪**。 已跟踪的文件是指那些被纳入了版本控制的文件，在上一次快照中有它们的记录，在工作一段时间后， 它们的状态可能是未修改，已修改或已放入暂存区。简而言之，已跟踪的文件就是 Git 已经知道的文件。

 工作目录中除已跟踪文件外的其它所有文件都属于未跟踪文件，它们既不存在于上次快照的记录中，也没有被放入暂存区。 初次克隆某个仓库的时候，工作目录中的所有文件都属于已跟踪文件，并处于未修改状态，因为 Git 刚刚检出了它们， 而你尚未编辑过它们。

 编辑过某些文件之后，由于自上次提交后你对它们做了修改，Git 将它们标记为已修改文件。 在工作时，你可以选择性地将这些修改过的文件放入暂存区，然后提交所有已暂存的修改，如此反复。

<img src="C:\Users\xunhi\AppData\Roaming\Typora\typora-user-images\image-20230520151436818.png" alt="image-20230520151436818" style="zoom:50%;" />

有关git历史请见：https://git-scm.com/book/zh/v2/%E8%B5%B7%E6%AD%A5-Git-%E7%AE%80%E5%8F%B2

### git的基本使用

>  git init

初始化git仓库，使用这个命令之后会获得一个`.git`文件。此时你的项目还没有被跟踪。

> git clone

克隆已有的仓库 ，Git 克隆的是该 Git 仓库服务器上的几乎所有数据，而不是仅仅复制完成你的工作所需要文件。 当你执行 `git clone` 命令的时候，默认配置下远程 Git 仓库中的每一个文件的每一个版本都将被拉取下来。 

例如：`git clone https://github.com/libgit2/libgit2`

这会在当前目录下创建一个名为 “libgit2” 的目录，并在这个目录下初始化一个 `.git` 文件夹， 从远程仓库拉取下所有数据放入 `.git` 文件夹，然后从中读取最新版本的文件的拷贝。 如果你进入到这个新建的 `libgit2` 文件夹，你会发现所有的项目文件已经在里面了，准备就绪等待后续的开发和使用

`git clone`会自动为你添加远程仓库，并且命名为`origin`

> git fetch <remote>

这个命令会访问远程仓库，从中拉取所有你还没有的数据。 执行完成后，你将会拥有那个远程仓库中所有分支的引用，可以随时合并或查看。

> git add

将文件添加到暂存区，可用`git add -A`来添加所有文件

> git commit

提交暂存区文件，通常使用`git commit -m "some massage"`

有时候我们提交完了才发现漏掉了几个文件没有添加，或者提交信息写错了。 此时，可以运行带有 `--amend` 选项的提交命令来重新提交，例如

```console
$ git commit -m 'initial commit'
$ git add forgotten_file
$ git commit --amend
```

最终你只会有一个提交——第二次提交将代替第一次提交的结果。

>  git status

查看当前文件处于什么状态，可以用`git status -s`来获得更加紧凑的输出

`git status`输出例子（刚刚执行完`git clone`之后）

```console
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
nothing to commit, working directory clean
```

`git status -s`输出例子

```console
$ git status -s
 M README
MM Rakefile
A  lib/git.rb
M  lib/simplegit.rb
?? LICENSE.txt
```

新添加的未跟踪文件前面有 `??` 标记，新添加到暂存区中的文件前面有 `A` 标记，修改过的文件前面有 `M` 标记。 输出中有两栏，左栏指明了暂存区的状态，右栏指明了工作区的状态。例如，上面的状态报告显示： `README` 文件在工作区已修改但尚未暂存，而 `lib/simplegit.rb` 文件已修改且已暂存。 `Rakefile` 文件已修改，暂存后又作了修改，因此该文件的修改中既有已暂存的部分，又有未暂存的部分。

> git log

回顾提交历史。不传入任何参数的默认情况下，`git log` 会按时间先后顺序列出所有的提交，最近的更新排在最上面。 正如你所看到的，这个命令会列出每个提交的 SHA-1 校验和、作者的名字和电子邮件地址、提交时间以及提交说明。按`q键`退出。

>  git remote add <shortname> <url>

添加远程仓库


> git remote

查看你的远程仓库名字，可用`git remote -v`来获得更加详细的信息

> git push <remote> <branch>

只有当你有所克隆服务器的写入权限，并且之前没有人推送过时，这条命令才能生效。 当你和其他人在同一时间克隆，他们先推送到上游然后你再推送到上游，你的推送就会毫无疑问地被拒绝。 你必须先抓取他们的工作并将其合并进你的工作后才能推送。

> git pull



> git merge

合并分支

> git branch 

创建分支

>git checkout

切换分支



`git`分支详细教程：https://git-scm.com/book/zh/v2/Git-%E5%88%86%E6%94%AF-%E5%88%86%E6%94%AF%E7%9A%84%E6%96%B0%E5%BB%BA%E4%B8%8E%E5%90%88%E5%B9%B6



