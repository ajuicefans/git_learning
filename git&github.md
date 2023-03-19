视频地址：[Git工作流和核心原理 | GitHub基本操作 | VS Code里使用Git和关联GitHub](https://www.bilibili.com/video/BV1r3411F7kn/?spm_id_from=333.999.0.0&vd_source=f111e229e8ddffc692d57d989194e313)

---

# Git核心原理

![1](https://raw.githubusercontent.com/ajuicefans/git_learning/main/images/1.png)

![2](https://raw.githubusercontent.com/ajuicefans/git_learning/main/images/2.png)

---



# Git实操

### 用户设置

```
# 设置用户名
git config --global user.name "ajuicefans"
# 设置邮箱
git config --global user.email ajuciefans@qq.com
```

### 初始化

```
git init
# 执行后，文件夹里就会多一个.git文件夹，这是一个隐藏文件夹，git的所有记录都会在这个文件夹里
```

初始化后的主分支一般为master

也可以把初始化时本地的默认分支改为main

```
git config --global init.defaultBranch main
```

---

> 执行git push 的时候遇到了OpenSSL SSL_read: Connection was reset, errno 10054，的错误提示
>
> 这是服务器的SSL证书没有经过第三方机构的签署，所以报错；错误原因可能是网络不稳定，连接超时造成的
>
> 如果你试了多次还是报这个错误，建议你执行下面的命令
>
> ```
> git config --global http.sslVerify "false"
> git config --global https.sslVerify "false"
> 
> ```
>
> 或在git配置文件 config 中加入以下代码
>
> ```
> [http]
>  	sslverify = false
> [https]
>  	sslverify = false
> ```

---

### `git status`

告诉你当前所处分支；还会告诉你文件的状态

- Untracked files：未追踪文件，处于工作区，需要进行 `git add` 操作添加到缓存区

- nothing to commit, working tree clean：执行了`git commit`操作后，已经添加到了本地版本库

> 下面的两个提示，如果出现相同内容，则是**在提交内容到暂存区，还没来得及提交到本地版本库时**，==**又对工作区的内容修改**==时，会同时出现

- Changes to be committed：可以提交到本地版本库
- Changes not staged for commit：已经发生变化，但还没提交到暂存区的内容

### `git add`

### `git commit`

`git commit -a -m "xxx"`或 `git commit -am "xxx"`：从工作区一下跳到本地版本库

### `git log`

查看前面提交到本地版本库的版本

除了提交者和时间和版本描述，还有哈希数字（代表着每次不同的commit）

### `.gitignore`文件

在 `.gitignore` 文件里添加图片的名字和后缀，可以表示我们要忽略的文件

这个时候 `git status` 就看不到图片未追踪的提示了



### 分支

####  `git branch`：查看分支

#### `git branch 分支名`：创建分支

#### `git checkout 分支名`：切换分支

第一次切换过来后的文件是直接从主分支复制来的，这时候动该分支下的文件，不会影响到主分支

`git checkout -b temp`：创建分支并且切换到该分支

#### `git branch -d`和`git branch -D`：删除分支

`-d`：当该分支还为和主分支合并，删除时会有提示

`-D`：会直接删除掉，没有提示

#### `git merge`：把别的分支合并到当前所处的分支上

##### 冲突：当前位置 和 合并的分支内容==同时修改，但是依旧不同==的地方

- 可以自己修改，选择需要的即可
- 也可以用一些merge工具来处理

---



## Github

