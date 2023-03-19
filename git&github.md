视频地址：[Git工作流和核心原理 | GitHub基本操作 | VS Code里使用Git和关联GitHub](https://www.bilibili.com/video/BV1r3411F7kn/?spm_id_from=333.999.0.0&vd_source=f111e229e8ddffc692d57d989194e313)

---

# Git核心原理

![1](F:/lifeProject/typora/git_test/git&github/images\1.png)

![2](F:/lifeProject/typora/git_test/git&github/images\2.png)

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

