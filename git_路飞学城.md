视频地址：[git_路飞学城](https://www.bilibili.com/video/BV1yQ4y1Y7jR/?spm_id_from=333.1007.top_right_bar_window_custom_collection.content.click&vd_source=f111e229e8ddffc692d57d989194e313)



## 01 Git是什么？

- 分布式

- 版本控制

  比如：毕业论文：初版、初稿、修改版、最终版

  - ①文件直接拷贝：所有版本的文件都能看到
  - ②本地版本控制：只能看到1份文件，其他版本都偷偷存起来了（电脑上看不到很多文件了，只能看到最新版本的文件）
  - ③集中式版本控制 SVN
  - ④分布式版本控制 Git

- 软件👉工具



## 02 为什么要做版本控制？

好做版本切换👉方便



## 03 安装git

git只能在本地（自己电脑上）做版本控制，然后再推送到远程仓库

> [git官网](https://git-scm.com/)

- Liunx 一行命令
- Windows 和 MacOS 用安装包安装

```
# 查看git版本
	git --version
```



## 04 git管理初期（仅在本地管理）

个人信息配置（执行一次即可）

```
git config --global user.email "you@example.com"
git config --global user.name "your name"
```



版本控制→git管理文件夹

1. 进入git要管理的文件夹

2. 初始化（提名）

   ```
   git init
   # 执行后出现 .git 文件夹
   ```

3. 管理

   ```
   # 检测当前文件夹下的文件状态
   git status
   # 注：新增的文件和修改过后的文件都是红色
   ```

   ```
   # 将文件提交到暂存区，即用git把文件管起来！（红色文件变绿色）
   git add [filename]	# 单个文件
   git add .			# 所有文件
   ```

4. 生成版本

   ```
   # 生成版本
   git commit -m '描述信息'
   ```

   ```
   # 查看版本记录
   git log
   ```

   

## 05 除此运行git需注意

个人信息的配置



## 06 git 三大区域

![2](https://raw.githubusercontent.com/ajuicefans/git_learning/main/images/2.png)



## 07 回滚

回滚到之前的版本

```
git log
git reset --hard 版本号
```

回滚到之后的版本（回退之后，又要再往后到新版本）

```
git reflog
git reset --hard 版本号
```



## 08 git命令小总结

![3](https://raw.githubusercontent.com/ajuicefans/git_learning/main/images/3.png)



## 09 初识分支：做环境的隔离

分支可以给使用者提供多个环境，意味着你可以把你的工作从开发主线上分离出来，以免影响开发主线



## 10 紧急修复线上bug的思路

bug分支：修复bug

创建一个bug分支，修复bug，修复以后，再合并到主分支

---



## 11 基于分支修复线上bug的具体过程

![4](https://raw.githubusercontent.com/ajuicefans/git_learning/main/images/4.png)

### 关于分支的命令总结

查看目前所处于的分支

```
git branch
```

创建分支

```
git branch 分支名
```

切换分支

```
git checkout 分支名
```

删除分支

```
git branch -d 分支名
```

把分支合并到目前所在的分支上

```
git merge 要合并的分支名

注：先切换分支，再合并
```

---

合并时如果产生冲突（不同分支修改过同一行数据时），要自己手动解决冲突

解决完冲突，再add、commit和push



## 12 工作流

- main 主干分支：正式版
- dev分支：做开发
- bug分支：修复bug
  - 创建一个分支，修复bug，修复以后，再合并到主分支



## 13 github

git 和 github 没有直接的关系

git 是版本控制的软件

github 是代码托管的仓库



使用github

1. 注册github账号
2. 创建仓库
3. 本地代码推送



## 14 基于github做代码托管

第一次把本地代码推送到远程仓库（github）

```
1. 给远程仓库起别名
    git remote add origin 远程仓库地址
2. 向远程推送代码
    git push -u origin 分支
    （这里的 -u 是默认提交到这个仓库的这个分支下）
```

第一次从远程仓库（github）获取代码

```
1. 克隆远程仓库代码（本地什么都没有的时候才clone）
    git clone 远程仓库地址
    （内部已经实现 git remote add origin 远程仓库地址）（默认的仓库别名就叫origin）
    （克隆时，分支也会克隆，只不过不显示，但是是可以切换到其他分支）
    
2. 切换分支
    git checkout 分支
```



## 15 奔波于家和公司之间~

在dev分支继续开发（dev分支开发时，要保持版本最新，即要先从main分支，merge一份到dev分支）

```
1. 切换到dev分支进行开发
    git checkout dev
2. 把main分支合并到dev（这时候dev分支上的代码也是最新的了）
    git merge main
3. 修改代码
4. 提交代码
    git add .
    git commit -m 'xxx描述'
    git push origin dev
```

回到家中继续写代码 + 到公司继续开发

```
1. 切换到dev分支进行开发
    git checkout dev
2. 拉代码（更新本地的代码）
    git pull origin dev
3. 继续开发
4. 提交代码（更新远程仓库的代码）
    git add .
    git commit -m 'xxx描述'
    git push origin dev
```

开发完毕，上线正式版本（即要把dev分支合并到main分支）

```
1. 将dev分支合并到main，进行上线（推送到远程仓库的main分支）
    git checkout main
    git merge dev
    git push origin main
    
2. 把dev分支也推送到远程仓库中的dev分支中
    git checkout dev
    git merge main
    git push origin dev

此时 main分支和dev分支都是最新的代码
```



## 16 有事忘记推送代码了

即忘记push到远程仓库了，此时在别的地方开发时，pull不到最新的代码了

继续开发其他功能，回到公司后，合并即可

### 合并时有共同修改的地方就会产生冲突

>  一样的自动保留，不一样的产生冲突

解决完冲突后，继续开发即可

```
git pull origin dev
==
git fetch origin dev
git merge origin/dev（远程仓库的dev） 
```

![5](https://raw.githubusercontent.com/ajuicefans/git_learning/main/images/5.png)

---



## 17-19 rebase应用场景以及注意事项

### rebase（变基）：使git记录变得简洁



### 第一种情况：把多个记录整合成一个记录

最新记录到 写上的版本整合成一个记录

```
git rebase -i 版本号 
```

整个 几个记录，就写几

```
git rebase -i HEAD~3
```

```
s 表示 让当前版本合并到上一个版本
```

退出编辑界面

```
:wq
```

提交整合后的提交信息



#### 注意事项：

提交到远程仓库的版本（push过的版本），先不要合并，即优先合并没有提交到远程仓库的版本👉否则容易造成非常麻烦的局面

---



### 第二种情况：将其他分支上的记录合并到某一分支（主分支）上

分支图像化的查看记录

```
git log --graph
```

分支图像化的、只看哈希值和记录的描述信息的查看记录

```
git log --graph --pretty=format:"%h %s"
```

---

先切回到dev分支

```
git checkout dev
```

rebase变基

```
git rebase main
```

切换回main分支，再merge回来

```
git checkout main
git merge dev
```

---



### 第三种情况：远程仓库pull产生分叉

将记录合并到一条分支上了

```
git pull 远程仓库别名 分支名
（git pull = git fetch + git merge）

改为写以下代码：fetch + rebase
git fetch 远程仓库别名 分支名
git rebase 远程仓库别名/分支名
```



### 注意事项：

以上三种情况都默认是没有冲突的

那如果有冲突怎么办？（`git rebase`产生冲突了怎么办？）

git会告诉你产生冲突了，去解决冲突

解决完后会提醒你执行`git add & commit`

再执行 `git rebase --continue`

---



## 20 beyond compare 快速解决冲突



## 21 命令总结



