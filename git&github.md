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



