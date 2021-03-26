git使用手册

安装git

在已经存在的目录下，输入

```shell
git init
#将该目录置于GIT的管理之下
ls -la
#发现一个.git的目录
```

```shell
#创建或修改本地文件
git add
#创建或修改的文件添加到本地暂存区
git commit
#将文件提交到本地仓库
git push
#本地代码库同步到远端仓库

```

![img](https://doc.shiyanlou.com/courses/uid8504-20190523-1558600871270)

```shell
mkdir Demo
cd Demo
gedit README.md
cat README.md
#利用git控制Demo目录
git init
ls -la
#将README.md暂存在本地暂存区
git add README.md
git status
#提交之前必须先设置你的名字和email，这是在你提交commit时的签名
git config --global user.name "tradoon"
git config --global user.email "xxxx@xx.com"
#提交到本地仓库 -m代表注释
git commit -m "first commit"
#将本地仓库内容提交到远程仓库，并给远程仓库去别名为origin
git remote add origin https://github.com/Tradoon/git
#将本地仓库推送到远程仓库汇总
git push origin master
#输入账号密码验证，即可完成
```

https://www.lanqiao.cn/courses/1330/learning/

```shell
#将远程仓库下载到本地
git clone https://github.com/你的Github账号/仓库名称 克隆仓库

```

对git进行本地配置：



```bash
git config --global user.name "tradoon"
git config --global user.email 
```

配置的内容将在根目录下生成Git配置文件.gitconfig

可以使用```git config -l```查看配置信息







```shell
git remote -v
#查看本地仓库关联的远程仓库的信息
```



git详细教程

```bash
git add fileName
#命令跟踪此文件，将文件加入到暂存区
git add .
#对多个目录或者文件进行了增删改查，将修改全部添加到暂存区
git reset -- fileName
git rm --cached fileName
#撤销文件在暂存区的修改
git reset -- 
#撤销对暂存区的全部修改

```

``` bash
git diff --cached
#查看暂存区中文件的修改
git log 
#查看版本区的提交历史记录
```

git log 详细介绍：https://www.lanqiao.cn/courses/1035/learning/?id=9805



git问题汇总：

# git报错：The TLS connection was non-properly terminated.

权限不足

git远程传送文件报错：

fatal: unable to access 'https://github.com/Tradoon/EB.git/': gnutls_handshake() failed: Error in the pull function.

解决方法：

git config --global --unset http.proxy

git config --global --unset https.proxy

问题：

```shell
 ! [rejected]        master -> master (fetch first)
error: failed to push some refs to 'https://github.com/Tradoon/git.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.

```

解决方法

```shell
 git pull origin master
 #显示 fatal: refusing to merge unrelated histories
 git pull origin master --allow-unrelated-histories
 git push origin master
```

