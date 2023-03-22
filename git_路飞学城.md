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



## 04 东北热创业初期

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