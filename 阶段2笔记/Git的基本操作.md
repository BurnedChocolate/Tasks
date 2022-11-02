

# Git基本操作

## 1.Git是什么？

✔**Git是一个分布式的服务系统**

> Git的三个主要概念：提交commit、仓库repository、分支branch

个人理解如下：

+ **提交commit**：Git会记录你每一次的代码变更，并且以*提交*的形式进行储存，以便后期进行回滚。
+ **仓库repository**：相当于文件夹，你的每一次提交是以仓库为基础进行的。
+ **分支branch**：利于开发者对不同部分的代码进行隔离。可以在代码中开辟不同的分支分配给不同的人写，最后在合并成一个完整的项目。

✔**Git 和 Git bash的区别**

Git是一个服务系统，而Git bash是Windows上的一个应用程序。后者允许开发人员在命令行界面中使用 Git。

使用示例如：在文件夹页面右键选择git bash here，即可在该文件夹中使用Git的命令行界面。

![](https://github.com/BurnedChocolate/Tasks/blob/main/%E9%98%B6%E6%AE%B52%E7%AC%94%E8%AE%B0/pictures/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202022-11-02%20194539.png?raw=true)

✔**在VScode中使用Git**

在VScode中使用快捷键ctel+ `打开终端，选择Git Bash即可在VScode中使用Git。

![](https://github.com/BurnedChocolate/Tasks/blob/main/%E9%98%B6%E6%AE%B52%E7%AC%94%E8%AE%B0/pictures/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202022-11-02%20212942.png?raw=true)

## 2.Git的基本操作

### 📕配置Git环境

```
git config --global user.name"在这里输入你的名字"
git config --global user.email"在这里输入你的邮箱"
```

设置一个新的用户，作为当前机器Git的标识。

### 📕git init：初始化一个仓库

```
git init
```

可以在空文件夹/已有文件夹内使用git init对该文件夹进行初始化。方法有两种：

1. 在你要进行初始化的文件夹内右键使用Git Bash，输入`git init`
2. 直接打开Git Bash，输入`git init` + 你要进行初始化的文件夹路径

操作成功后会看到这样一行文字：`Initialized empty Git repository in ` + 该文件夹的路径。

这样我们就有了一个空的git仓库。

### 📕git add和git commit：提交

在了解这两个命令之前，我们需要了解Git的另一个核心内容——三个**功能区**。它们是：工作区、暂存区、仓库（分本地仓库和远程仓库）。

| 功能区   | 解释                                                         |
| -------- | :----------------------------------------------------------- |
| 工作区   | 即打开文件夹后可以看到的部分，是程序员进行开发和改动的地方，*任何对象都在工作区中诞生和被修改* |
| 暂存区   | 暂存区会记录git add添加文件的相关信息，不保存文件实体，（通过id指向每个文件实体），*任何修改都从进入暂存区开始被版本控制*（可以使用git status查看暂存区的状态） |
| 本地仓库 | 保存了对象被提交过的*各个版本*                               |
| 远程仓库 | （GitHub远程仓库），其中的内容可被分布在多个地点的处于协作关系的本地仓库共享和修改 |

它们之间的联系是：**工作区**中的内容通过`git add`命令转存到暂存区中，**暂存区**中的内容又可以通过`git commit`命令储存到**本地仓库**中。（远程仓库的相关讨论见下文）

```
git add <filename>   #<filename>这里整个输入文件名
git add -A           #-A是all的意思，就是全选
git commit -m “提交的信息，在此处描述你这次提交的是什么东西，方便之后查看”
```

命令后面带的 -A、-m等是参数。

另外：

1. 文件夹中的`.git`隐藏文件不要删，你的所有历史提交都记录在里面。
2. VScode里还有不用命令行就能实现暂存和提交到仓库的图形化功能，感觉似乎更方便一点（）具体见截图。

![](https://github.com/BurnedChocolate/Tasks/blob/main/%E9%98%B6%E6%AE%B52%E7%AC%94%E8%AE%B0/pictures/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202022-11-02%20214753.png?raw=true)

![](https://github.com/BurnedChocolate/Tasks/blob/main/%E9%98%B6%E6%AE%B52%E7%AC%94%E8%AE%B0/pictures/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202022-11-02%20220314.png?raw=true)

### 📕git log：查看提交的历史

```
git log
git log --stat
```

加不加`--stat`参数会影响显示的提交历史的数据丰富程度，例如下图：

![](https://github.com/BurnedChocolate/Tasks/blob/main/%E9%98%B6%E6%AE%B52%E7%AC%94%E8%AE%B0/pictures/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202022-11-02%20221034.png?raw=true)

![](https://github.com/BurnedChocolate/Tasks/blob/main/%E9%98%B6%E6%AE%B52%E7%AC%94%E8%AE%B0/pictures/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202022-11-02%20221051.png?raw=true)

第一行黄色的commit是哈希算法算出的id，它是唯一的。

### 📕git checkout \<filename> 和 git reset HEAD^ ：反悔功能

```
git checkout <filename>
git reset HEAD^
```

`git checkout <filename>`用于对工作区里尚未提交的文件进行反悔，`git reset HEAD^`用于对已经提交到仓库里的东西进行反悔。`HEAD`指你当前的这个提交，`^`意思是定向到某一个，在`^`后添加数字（默认为1），也就指定向到HEAD的上一个，也就是你最近提交的文件。

### 📕git push和git pull：GitHub远程仓库

在进行这一步操作之前要进行漫长的SSH配置操作和关联远程仓库操作……有点复杂，写下来会用很多篇幅，然后因为已经配置好了这里就不多做笔记了（）具体见参考资料第二条中35分左右的视频讲解。

```
git push
git pull
```

`git push`是**推送到远程仓库**，`git pull`是**拉取到本地仓库**。

`git push`需要在`git add`和`git commit`命令完成后才能使用，相当于把远程仓库更新成本地仓库目前的状态。`git pull`就是反过来，可能有其他人更改了你远程仓库上的分支，这个命令可以把最新的远程仓库的状态拉取到本地。（很方便的功能呢）

值得注意的是，`git push`时，系统会自动检测你要推送的东西是否是相较于远程仓库里的文件的更新的状态。如果远程仓库里的更加的新，系统是不会让你push的（血的教训……）所以这种情况下，我们要**先pull，再push，达成本地和远程的双向更新**。

## 📖参考资料

+ [Git 教程 | 菜鸟教程](https://www.runoob.com/git/git-tutorial.html)
+ [40 分钟学会 Git | 日常开发全程大放送&搭配Github](https://www.bilibili.com/video/BV1db4y1d79C/)
+ [Git: 工作区、暂存区、本地仓库、远程仓库](https://blog.csdn.net/weixin_36750623/article/details/96189838)



