#git的简单实用和Github的简单介绍
这篇文章主要是用于记录我在开始使用 Git 时的一些常用的命令，和遇到某种情况下的解决办法。而不是系统、全面的讲解Git的使用。主要是记录一下，以后忘记了可以到这来加深印象。由于本屌丝用的 window 操作系统，那么下边讲到的内容都是基于 window 环境。

##1.git初识
git是一个版本管理工具，它的作用主要是为了人们更加方便的管理文件，这里的文件可以是一个一个项目，也是可以是一个.txt文件等等。那么赶快一起学习吧！！！

git的安装，不同的操作系统有不同的版本，不同的安装方法，自行百度，安装即可。那么接下来开始将git的使用了。

##2.git的使用
在我最开始学习git的时候，我认为如下：
创建git本地仓库 --> 在本地的仓库进行维护 --> 然后同步到远程的仓库。

###2.1 git本地仓库的初始化
右键选择 Git Bush Here,在弹出框中，新建一个目录，然后通过如下命令

    git init

此时，这个目录就变成了你的本地仓库，现在你就可以通过 git 来管理本地仓库了。

###2.2 git 常用操作

#### 2.2.1 git 新增文件提交过程

**1)**：使用 ** git add**  添加文件到暂存区。我们就添加一个 readme.txt 文件，如下：
  
    git add readme.txt

如果没有任何的提示，那么说明添加成功，你如果实在不放心，那你可以输入 **ll** 命令来查询当前目录下边的文件,如果你比较懒不想一个一个的添加，你可以使用 **git add . **,你没有看错，add后边跟一个小点，就会批量添加所有的文件，对于我这种懒人来说，肯定是比较爽的啦，嘿嘿^_^.

**2)**：使用  git commit 来提交文件到仓库，将 readme.txt 提交到仓库，如下：

    git commit -m "提交readme.txt文件"

需要注意的是 -m 后边的内容是你对于本次提交的说明，必须填写！必须填写！必须填写！重要的事说三遍！！！

**3)**：你提交了文件之后，想必你很想知道是否成功提交吧，这个时候可以通过 git status 命令来查看当前git仓库中文件的状态，比如哪些文件被修改了，哪些文件被删除了，那些文件是新增的等等。命令如下：

    git status

#### 2.2.2 git 修改文件提交过程

**1)**：使用之前提到的 ** git status** 命令，查看当前 git 仓库中文件的状态。

**2)**：对于你修改的文件，至少应该看看你自己修改的内容吧，使用 git diff 文件名+后缀，如下：

    git diff readme.txt

**3)**：继续使用 git add 命令，如下：

    git add readme.txt

到这个地方，不知道你们有没有疑惑，反正我最开始是不明所以的，add不是添加吗，为什么修改的文件还需要add，这个添加你可以认为是一种修改，因为你新建一个文件，也相当于一个修改，然后这个add命令是将你的修改 保存到一个暂存区，例如你add了一个文件之后，你突然觉得多余了，然后马上删掉，这样你再add，就代表将删除的这个修改动作保存到了暂存区，但是还未提交到本地仓库，这样可以提高效率。

**4)**：使用  git commit 来提交文件到仓库，将 readme.txt 提交到仓库，如下：

    git commit -m "第二次提交readme.txt文件"

**5)**：如果你提交了了多次，然后想查看提交的历史纪录，你可以使用 git log 命令：

    git log

如果你觉得显示每次提交的信息太多的话，你可以使用  git log -pretty=oneline 显示每次提交信息的第一行。

#### 2.2.3 git 版本回退
通过前面的学习，我们已经掌握了git新增和修改文件。但是，这点技能远远不够。在我们平时的开发中，特别是团队协作的开发过程中，肯定会遇到代码被覆盖的情况，所以，这个时候，我们需要一个版本回退的功能，放心，git都有。

**1）**：git 回退到上一个版本

    git reset --hard HEAH^

**2**: git 回退都上上个本版

    git reset --hard HEAD^^

**3**: git 回退到之前的第100个版本

    git reset --hard HEAD~100




最后，我推荐一片博客[http://www.cnblogs.com/tugenhua0707/p/4050072.html](http://www.cnblogs.com/tugenhua0707/p/4050072.html),本文中很多内容也是借鉴于此。
