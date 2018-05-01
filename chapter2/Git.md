# Study List
* [时光机穿梭 - 廖雪峰的官方网站](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)
* [远程仓库 - 廖雪峰的官方网站](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000/001374385852170d9c7adf13c30429b9660d0eb689dd43a000)
* [分支管理 - 廖雪峰的官方网站](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000/0013743862006503a1c5bf5a783434581661a3cc2084efa000)
* [标签管理 - 廖雪峰的官方网站](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000/0013762144381812a168659b3dd4610b4229d81de5056cc000)
# 创建SSH Key
```
ssh-keygen -t rsa -C "youremail@example.com"
$ ssh-keygen -t rsa -C "997948809@163.com"
Generating public/private rsa key pair.
Enter file in which to save the key (/c/Users/Administrator/.ssh/id_rsa): id_rsa_new
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in id_rsa_new.
Your public key has been saved in id_rsa_new.pub.
The key fingerprint is:
SHA256:Da0KisF+M1k0VHwB55EK6bYJzizfoDO6AeM8fKBdAbU 997948809@163.com
The key's randomart image is:
+---[RSA 2048]----+
|  ....+o.+o      |
|   ..+ .o+.      |
|    Eo. +..      |
|.  ..+.. +       |
|+o+ =.o S .      |
|B*.Bo+ .         |
|+***o .          |
| =+.o.           |
|+.o              |
+----[SHA256]-----+
```
window系统下.ssh目录
```
cd ~
cd .ssh
```
# Github访问慢解决办法
* 打开 http://tool.chinaz.com/dns ,这是一个查询域名映射关系的工具
* 查询 github.global.ssl.fastly.net 和 assets-cdn.github.com 两个地址
* 多查几次，选择一个稳定，延迟较低的 ip 按如下方式添加到host文件
* 保存文件，重新打开浏览器，起飞。
```host
# github
192.30.253.112 assets-cdn.github.com
151.101.88.249 github.global.ssl.fastly.net
```
# 本地版本库关联GitHub仓库
* git remote add
```
git remote add origin git@github.com:luojianet/gitreset.git
git push -u origin master
```
* git -u push origin master
```
$ git push -u origin master
Counting objects: 3, done.
Delta compression using up to 8 threads.
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 321 bytes | 321.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0)
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To github.com:luojianet/git.git
   4a23a7b..3ec2e91  master -> master
Branch 'master' set up to track remote branch 'master' from 'origin'.
```
* git push

```
$ git push
fatal: No configured push destination.
Either specify the URL from the command-line or configure a remote repository using

    git remote add <name> <url>

and then push using the remote name

    git push <name>
```
* git push(have add origin)

```
$ git push
fatal: The current branch master has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin master
```
# Commond Line
* git config --global user.name 

```
git log -5 --pretty="%h - %an %s"
git log -5 --pretty --oneline
git config --global user.name ""
git config --global user.emal ""
git config --list
git config -l
```
* git log --pretty=oneline -10

```
$ git log --pretty=oneline -10
a6e440676f10f200b0ebd13ef6b66255d45d7df4 (HEAD -> master, origin/master) git show #commit fileName
de1af27db59b734de31ba0a16c3825bf02887c75 version3
23d90d5ab352761b875fe6c3959f9bd3086b7efc version2
b15a3bedbcfcbe7025dfb0f640008a92d41ed3a2 version1
746d45cc1eac434836feb331bd1ce4cd87cad821 rm file.txt
2263e878410d717b66cc5cda0faa737db3c42303 version3
14d7e666ab87eba36f865218608372e38c1ebee8 version2
ae9e85fc1cc056f5871389e75b7b2976585cac10 verson1
82014c4dd656b48dc7fd7dbe400b3205c6d434f3 增加一条笔记
571e5ba0ac2efe45b8b48c48b242798d408cbb1e 为版本回退做准备
```
* git show #commit fileName

```
$ git show 23d90d5ab352761b875fe6c3959f9bd3086b7efc first.txt
commit 23d90d5ab352761b875fe6c3959f9bd3086b7efc
Author: luojianet <997948809@163.com>
Date:   Mon Apr 9 12:53:43 2018 +0800

    version2

diff --git a/example/first.txt b/example/first.txt
index d8036c1..013b5bc 100644
--- a/example/first.txt
+++ b/example/first.txt
@@ -1,2 +1,2 @@
-Git is a version control system.
+Git is a distributed version control system.
 Git is free software.
\ No newline at end of file
```

* git reset --hard HEAD^\|git reset --hard HEAD~

```
$ git reset --hard HEAD^
HEAD is now at de1af27 version3

Administrator@yanhu MINGW64 /c/github/git (master)
$ git reset --hard HEAD~
HEAD is now at 23d90d5 version2
```

* git diff origin/master -- README.md
```
$ git diff origin/master -- README.md
diff --git a/README.md b/README.md
index af6b8df..273b7f6 100644
--- a/README.md
+++ b/README.md
@@ -69,4 +69,7 @@ HEAD is now at 23d90d5 version2
 * git reset --hard HEAD^|git reset --hard HEAD^^^^|git reset --hard HEAD~|git reset --hard HEAD~3
 * --hard选项会忽略本地修改，回退到指定版本，没有这个选项会提示`Unstaged changes after reset:`
 * git reset --hard #commit id,版本号没必要写全，前几位就可以了，Git会自动去找。回退到指定commit id，需要最少是4位commit id，从前向后4位。
-* Git提供了一个命令`git reflog`用来记录你的每一次命令：
\ No newline at end of file
+* Git提供了一个命令`git reflog`用来记录你的每一次命令：
+* 工作区有一个隐藏目录`.git`，这个不算工作区，而是Git的版本库。Git的版本库里存了很多东西，其中最重要的就是称为stage（或者叫index）的暂存区，还有Git为我们自动创建的第一个分支`master`，以及指向`master`的一个指针叫`HEAD`。
+* 第一步是用`git add`把文件添加进去，实际上就是把文件修改添加到暂存区；第二步是用`git commit`提交更改，实际上就是把暂存区的所有内容提交到当前分支。
+* Git跟踪并管理的是修改，而非文件。你会问，什么是修改？比如你新增了一行，这就是一个修改，删除了一行，也是一个修改，更改了某些字符，也是一个修改，删了一些又加了一些，也是一个修改，甚至创建一个新文件，也算一个修改。
\ No newline at end of file
```

* 解决冲突

```
git merge dev
<<<<<<< HEAD
master 分支修改
=======
dev 分支修改
>>>>>>> dev

git merge master
<<<<<<< HEAD
dev 分支修改
=======
master 分支修改
>>>>>>> master
```
* git log --pretty=oneline --graph --abbrev-commit -10

```
$ git log --graph --pretty=oneline --abbrev-commit -10
* 70a3a94 (HEAD -> master, origin/master) git stash pop
*   efaa7af 主分支修改了两次，开发分支修改了1次，解决冲突
|\
| * 6f9b154 (dev) git merge总结
| *   4279bc9 合并主分支commit
| |\
* | | 1018e41 主分支修改了2次，把dev合并过来
* | | cfcc467 同时修改两个分支，禁用no-ff
| |/
|/|
* |   e62967e 这是一个使用no-ff参数的分支合并commit
|\ \
| |/
| * 86516aa 可以不用关心参数顺序嘛
| * 2a198f7 准备合并dev分支，请注意--no-ff参数，表示禁用Fast forward：
|/
* 5c28fbe 禁用Fast forward
```
* master分支提交点，**提交点**,左侧竖线是当前分支

```
$ git log --pretty=oneline -20 --abbrev-commit --graph
*   5d00a9f (HEAD -> master) 合并dev分支到master分支，解决README.md文件冲突
|\
| * 3d781e9 修改版本号
| * 51faa52 不用在master分支上开发
* | d99d591 (origin/master) git log --abbrev-commit
* | 976e27c git log --abbrev-commit
* | 70a3a94 git stash pop
* |   efaa7af 主分支修改了两次，开发分支修改了1次，解决冲突
|\ \
| |/
| * 6f9b154 git merge总结
| *   4279bc9 合并主分支commit
| |\
* | | 1018e41 主分支修改了2次，把dev合并过来
* | | cfcc467 同时修改两个分支，禁用no-ff
| |/
|/|
* |   e62967e 这是一个使用no-ff参数的分支合并commit
|\ \
| |/
| * 86516aa 可以不用关心参数顺序嘛
| * 2a198f7 准备合并dev分支，请注意--no-ff参数，表示禁用Fast forward：
|/
* 5c28fbe 禁用Fast forward
*   e83df15 Merge branch 'dev'
|\
| * 995fa33 this is dev branch.
|/
* 7b53b0a ff
*   11925ec Merge branch 'dev'
|\
| * f2b00de dev
```
* dev分支提交点**提交点**,左侧竖线是当前分支

```
$ git log --pretty=oneline -20 --abbrev-commit --graph
* 665cce2 (HEAD -> dev) 算数运算3*6
*   1c90c35 合并master分支到dev分支，继续开发修改bug之前的算数运算
|\
| *   5d00a9f (master) 合并dev分支到master分支，解决README.md文件冲突
| |\
| |/
|/|
* | 3d781e9 修改版本号
* | 51faa52 不用在master分支上开发
| * d99d591 (origin/master) git log --abbrev-commit
| * 976e27c git log --abbrev-commit
| * 70a3a94 git stash pop
| *   efaa7af 主分支修改了两次，开发分支修改了1次，解决冲突
| |\
| |/
|/|
* | 6f9b154 git merge总结
* |   4279bc9 合并主分支commit
|\ \
| | * 1018e41 主分支修改了2次，把dev合并过来
| | * cfcc467 同时修改两个分支，禁用no-ff
| |/
| *   e62967e 这是一个使用no-ff参数的分支合并commit
| |\
| |/
|/|
* | 86516aa 可以不用关心参数顺序嘛
* | 2a198f7 准备合并dev分支，请注意--no-ff参数，表示禁用Fast forward：
|/
* 5c28fbe 禁用Fast forward
*   e83df15 Merge branch 'dev'
|\
| * 995fa33 this is dev branch.
|/
* 7b53b0a ff
```
* git stash

```
$ git stash
Saved working directory and index state WIP on dev: 5aeaf69 应用某个stash
```
* git stash pop

```
$ git stash pop
On branch dev
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
Dropped refs/stash@{0} (1abc634d2849eb858d6a30d6a4ab353758d782fa)
```
* 配置别名

```
Administrator@yanhu MINGW64 /c/github/FEbook (master)
$ git config --global alias.st status

Administrator@yanhu MINGW64 /c/github/FEbook (master)
$ git st
On branch master
Your branch is ahead of 'origin/master' by 2 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
```

# 笔记
* git init本地初始化一个版本库
* 如果嫌输出信息太多，看得眼花缭乱的，可以试试加上`--pretty=oneline`参数
* git log --pretty=oneline -10
* git show #commit fileName
* git reset --hard HEAD^|git reset --hard HEAD^^^^|git reset --hard HEAD~|git reset --hard HEAD~3
* --hard选项会忽略本地修改，回退到指定版本，没有这个选项会提示`Unstaged changes after reset:`
* git reset --hard #commit id,版本号没必要写全，前几位就可以了，Git会自动去找。回退到指定commit id，需要最少是4位commit id，从前向后4位。
* Git提供了一个命令`git reflog`用来记录你的每一次命令：
* 工作区有一个隐藏目录`.git`，这个不算工作区，而是Git的版本库。Git的版本库里存了很多东西，其中最重要的就是称为stage（或者叫index）的暂存区，还有Git为我们自动创建的第一个分支`master`，以及指向`master`的一个指针叫`HEAD`。
* 第一步是用`git add`把文件添加进去，实际上就是把文件修改添加到暂存区；第二步是用`git commit`提交更改，实际上就是把暂存区的所有内容提交到当前分支。
* Git跟踪并管理的是修改，而非文件。你会问，什么是修改？比如你新增了一行，这就是一个修改，删除了一行，也是一个修改，更改了某些字符，也是一个修改，删了一些又加了一些，也是一个修改，甚至创建一个新文件，也算一个修改。
* git diff origin/master -- README.md 对比本地文件和远程分支
* git diff HEAD  -- README.md 对比本地文件和本地master分支
* 第一次修改 -> git add -> 第二次修改 -> git commit。你看，我们前面讲了，Git管理的是修改，当你用git add命令后，在工作区的第一次修改被放入暂存区，准备提交，但是，在工作区的第二次修改并没有放入暂存区，所以，git commit只负责把暂存区的修改提交了，也就是第一次的修改被提交了，第二次的修改不会被提交。
* `git diff` ,`git diff HEAD`,`git diff origin/master`比较修改，工作区和暂存区，工作区和本地版本库，工作区和远程版本库
* `git checkout -- file`命令中的`--`很重要，没有`--`，就变成了“切换到另一个分支”的命令。
* 回退工作区，回退暂存区，回退版本库
* git checkout -- file丢弃工作区的修改
* git reset HEAD|git reset|git reset HEAD -- file回退暂存区
* git reset HEAD^丢弃一个commit，回退到工作区（只可以操作还没push的commit）
* git reset --hard HEAD丢弃工作区修改，丢弃暂存区修改
* git reset --hard HEAD^回退上一版本，丢弃工作区修改
* git [-u | --set-upstream]
```
git remote add origin git@github.com:luojianet/gitreset.git
git push -u origin master
```
* 实际上，Git支持多种协议，默认的`git://`使用ssh，但也可以使用`https`等其他协议。使用`https`除了速度慢以外，还有个最大的麻烦是每次推送都必须输入口令，但是在某些只开放http端口的公司内部就无法使用`ssh`协议而只能用`https`。
* 一开始的时候，`master`分支是一条线，Git用`master`指向最新的提交，再用`HEAD`指向`master`，就能确定当前分支，以及当前分支的提交点。
* git checkout -b branchName,git checkout命令加上-b参数表示创建并切换分支
* git branch -d dev删除分支
* git merge --abort
* 发生冲突时，冲突的上面部分HEAD指向当前分支，下面指向合并过来的分支
* 用`git log --graph`命令可以看到分支合并图。
* 通常，合并分支时，如果可能，Git会用`Fast forward`模式，但这种模式下，删除分支后，会丢掉分支信息。如果要强制禁用`Fast forward`模式，Git就会在merge时生成一个新的commit，这样，从分支历史上就可以看出分支信息。
* 准备合并`dev`分支，请注意`--no-ff`参数，表示禁用`Fast forward`：`$ git merge --no-ff -m "merge with no-ff" dev`
* git log --abbrev-commit
* `不要在master分支上开发`
* `git stash`,`git stash pop`,`git stash apply`,`git stash list`
* 确定要在哪个分支上修复bug，假定需要在`master`分支上修复，就从`master`创建临时分支
* Git把stash内容存在某个地方了，但是需要恢复一下，有两个办法：一是用git stash apply恢复，但是恢复后，stash内容并不删除，你需要用git stash drop来删除；另一种方式是用git stash pop，恢复的同时把stash内容也删了：
* 你可以多次stash，恢复的时候，先用git stash list查看，然后恢复指定的stash，用命令：`git stash apply stash@{0}`
* 开发一个新feature，最好新建一个分支；如果要丢弃一个没有被合并过的分支，可以通过`git branch -D <name>`强行删除。
* 当你从远程仓库克隆时，实际上Git自动把本地的`master`分支和远程的`master`分支对应起来了，并且，远程仓库的默认名称是`origin`。或者，用`git remote -v`显示更详细的信息。下面显示了可以抓取和推送的origin的地址。如果没有推送权限，就看不到push的地址。
```
$ git remote -v
origin  git@github.com:michaelliao/learngit.git (fetch)
origin  git@github.com:michaelliao/learngit.git (push)
```
* 推送分支，就是把该分支上的所有本地提交推送到远程库。推送时，要指定本地分支，这样，Git就会把该分支推送到远程库对应的远程分支上：`git push origin master`
* 创建远程`origin`的`dev`分支到本地，于是他用这个命令创建本地`dev`分支：`git checkout -b dev origin/dev`
* 敲命令`git tag <name>`就可以打一个新标签,可以用命令`git tag`查看所有标签,给某个commit打标签`git tag v0.9 6224937`
* 别名：敲`git st`就表示`git status`，`co`表示`checkout`，`ci`表示`commit`，`br`表示`branch`