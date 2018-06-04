## 十分钟了解Git干货版

### 1.为什么使用git?

​	a) 非常有利于自己知识和经验的积累

​	b)能够通过git展示工作经验和分享交流自己的项目

​	c)能够通过git管理团队和项目

### 2.为什么选git?

​	a)好用

​	b)无缝的提交到github等平台

### 3.git和github的关系？

​	git是一个版本控制工具
​	github是一个用git做版本控制的项目托管平台。

### 4.git 几个重要的概念

​	这里类比一下

​	仓库（书店）：所有版本的代码都在仓库（所有版本的《金瓶梅》都在书店里）

​	分支（书架）：不同功能功能的代码存放的地方（我把《金品梅》插图版和古装版放在不同的书架，这样可以互不干扰）

​	提交（书）：每一个版本的代码 （《金瓶梅》插图版 第一版印刷，第二版印刷……）

### 5.核心重点基础内容怎么玩

​	官网：https://git-scm.com/  git是可以装在自己电脑或者服务器的，不墨迹开整

​	1.新建一个文件夹helloGit,进入

​	2.右键gitBash,创建仓库，

```
git init
```

​	3.创建一个a.txt，打开里面内容随便造。

​	4.输入

```
git status
```

看一下git的状态，这个命令牛逼之处就是告诉你接下来该怎么做，人家说了你没把a.txt交给仓库去管。

​	5.将所有文件加入到缓存区(相当于你把文件交给管理员了)，

```
git add .
```

​	6.将文件 提交到仓库（管理员把你的文件扔仓库里了），

```
git commit -m '这里是写点注释，省的你不知道自己提交了啥内容，这是第一次提交'
```

这样一次提交就完成了，

​	7.打开a.txt 随便加点内容，继续造，然后

```
git add .
git commit -m '第二次提交'
```

​	8.我们看看我们提交了几个版本，

```
git log  
```

这里我们提交的两次就看到了,而且能看到commit后面的id 。我要想回到第一次提交咋整，

```
git checkout c0f259e284a27c1871562631bd9753d46f5798bb
```

打开a.txt 看看，回到第一个版本了。到现在你已经会了，提交多个版本，回滚到某个版本。我想回到上一个版本老找id忒费事，可以用这个

```
git checkout -- .
```

### 6.说点进阶的玩法-分支

​	大家考虑这么一个情况，假如你是angularjs开发团队，你想angular2.0基于angularjs开发，但是有特别大的革命性变化，你说咋办好？

​	这时候你看这样合不合理，我分一部分人负责原angularjs的基础维护和平滑升级，然后复制一份angularjs让另外一个团队进行革命性开发，这样两个团队都不互相干扰，等2.0的功能开发完成了，我再融合到原来的angularjs里面去。这个就是分支的功能。

​	1.我先复制一份原来的东西，开一个新的分支

```
git checkout -b new-fenzhi
```

​	我们看看现在有几个分支，

```
git branch	
```

大家可以看到这里有两个分支，一个master,一个new-fenzhi，

新建b.txt的内容,然后 

```
git add .
git commit -m '我在新分支上糟蹋的'
```

注意，这时候我们删除b,我们回到master分支，看看它影响master不，

```
git checkout master
git log
```

大家可以看到 根本就没有影响master，master下是没有b.txt 我们假设搞完了，把git new-fenzhi的东西合并回master咋整，

```
git merge new-fenzhi
```

这样就合并回去了。

### 7.说下git和github一起玩。

​	1.最简单把github项目搞下来

```
git clone  xxxxx.git
```

​	2.提交到github.

```
git remote add origin https://github.com/breaddream/helloGit.git
git push -u origin master
```

这里注意，如果提示orgin 已经存在，就先把远程的仓库删除再执行，

```
git remote rm origin
```





​	