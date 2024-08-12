# Git

## 1. 用户信息

配置用户信息

```shell
git config --global user.name 'acha'
git config --global user.email 'wz.0527@qq.com'
git config --global color.ui true
```

查看用户信息

```shell
[root@gitbook ~]# cat .gitconfig 
[user]
        name = acha
        email = wz.0527@qq.com
[color]
        ui = true
```



## 2. 初始化目录结构

```shell
[root@gitbook xx]# tree .git/
.git/
├── branches  # 分支目录
├── config    # 项目配置选项
├── description #仅供 git web 程序使用
├── HEAD    # 指示当前分支
├── hooks   # 钩子
├── info    # 有一个排除文件
├── objects # 存放所有数据
├── index   # 暂存区信息
└── refs    # 指向数据提交对象的指针
```

文件存放位置，相互隔离

- 工作目录
- 暂存区
- 本地仓库
- 远程仓库



## 3. 常见命令

```shell
git init 
# 初始化 工作目录

git status
# 查看 git 状态

git add .
# 添加 工作目录所有文件 到 暂存区

git rm --cached <file>
# 撤出 暂存区中的 文件

git commit -m "tip"
# 暂存区 提交到 本地仓库

git commit -am "add newfile"
# 修改 工作目录中本地仓库 已存在文件

git diff 
# 比对 工作目录 暂存区

git diff --cached
# 比对 暂存区 本地仓库

git log
# 提交日志

git log --oneline -1
# 提交日志 显示最近一次

git reset --hard <id> | <tag>
# 回滚

git branch
# 查看分支

git branch <name>
# 新建分支

git checkout -b <branch>
# 切换分支,不存在则新建

git merge <branch>
# 合并 分支到主分支

git tag -a <version> <id> -m "tip"
# tag

git tag show <tag>
# 查看 tag 信息

git remote
# 查看远程仓库

git remote add <name> <url>
# 添加远程仓库

git push -u <remote> <local-branch>
```