# Git学习心得

这两天在技术部学姐的指导下看了峰哥的Git，不得不说这真是太有意思了，现已学习内容有

* 环境搭建
* 版本选择
* 远程仓库
* 分支管理

~~分支学到一半还没学完，只好随便写写了~~

## 环境搭建

### 安装+创建版本库

* **安装后的配置**

  ```
  $ git config --global user.name "Your Name"
  $ git config --global user.email "email@example.com"
  ```

* **创建版本库**

  ```
  $ mkdir learngit # 创建空目录
  $ cd learngit # 跳转到某个目录
  $ pwd # 显示当前目录
  $ git init # 将该目录变成Git可管理的仓库
  ```

* **代码补充**

1. `cd ..` 回到上级目录
   - cd和..之间有空格
2. `rm <file>` 删除文件

   - 删除后需使用`git rm <file> ` 才能将该文件在Git的版本库中删除

* ***注意事项***
  1. 确保仓库的地址中不含中文
  2. 若仓库放在用户的文件夹里且用户名包含中文，修改了用户名后要在注册表里重命名文件夹

### **添加文件进入仓库**

* **添加文件到仓库**

  ```
  $ git add <file>
  ```

* **提交文件到仓库**

  ```
  $ git commit -m "message"
  ```

* ***注意事项***

  1. `git add` 后要记得 `git commit`
  2. `git commit` 要加上有意义的说明



## 版本选择

### 原理说明

![alt 原理](https://static.liaoxuefeng.com/files/attachments/919020037470528/0)

* **工作区、暂存区和版本库**
  1. 工作区（Working Directory）：电脑里能看见的目录
  2. 暂存区（Stage）：`git add <file>` 后 `git commit` 前，文件修改存放的地方
  3. 版本库（Repository）：版本库里包含了暂存区和commit过的修改
* **HEAD**
  1. `HEAD `是一个**指针**，它指向当前最新的版本
  2. `HEAD^` 表示上一个版本`HEAD^^` ，`HEAD ~100` 表示上100个版本

### **关于查看相关信息的代码**

```
$ git status # 掌握仓库当前的状态
$ git diff # 查看具体修改了那些内容
$ git diff HEAD --<file> # 查看工作区和版本库里最新版本的区别
$ git log # 用于回到过去（显示最近到最远的提交日志）
$ git reflog # 用于重返未来（查看命令历史）
```

* **补充说明**
  1. 在 `git log` 后加上 `--pretty=one` 可以更加美观些（不要乱加空格T^T）
  2. 在 `git log` 后加上 `--graph` 可以查看分支合并图

### 后悔药的服用方法

```
$ git reset --hard HEAD^ # 回到上个版本
$ git reset --hard commit-id # 利用版本号回到某个版本
$ git checkout --<file> # 丢掉工作区里的东西
$ git reset HEAD <file> # 丢掉暂存区里东西（丢完还要再丢工作区的）
```



## 远程仓库

### Github上的操作

* 注册账号
* Add SSH Key
* 在Github上创建仓库

### 本地上的操作

* **添加远程仓库**

  ```
  $ git remote add origin https://github.com/LmyLeo/learngit.git # 举个梨子
  ```

* **将本地库的内容推送到远程仓库**

  ```
  $ git push -u origin master # 第一次要加上 -u，后面就不用加了
  $ git push origin master
  ```

* **克隆远程仓库**

  ```
  $ git clone https://github.com/LmyLeo/cookie-box.git # 举个梨子
  ```

  

## 分支管理

### 初识分支

* **个人理解**
  * 类似平行宇宙的东西
  * 便于修复bug
  * 便于多人协作

* **相关代码**

  ```
  $ git branch # 查看分支
  $ git branch <name> # 创建分支
  $ git switch <name> # 切换分支
  $ git checkout <name> # 切换分支
  $ git switch -c <name> # 创建+切换
  $ git checkout -b <name> # 创建+切换
  ```

  









