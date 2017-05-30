# git 命令教程
> git是一种最先进的分布式版本控制系统（没有之一）。
> git是Linus Benedict Torvalds 用C写的，Linux系统的源码已经由Git管理。尤其是2008年，GitHub网站上线了，它为开源项目免费提供Git存储，无数开源项目开始迁移至GitHub，包括jQuery，PHP，Ruby, Swift等等。

******

## 创建版本库：
1. 版本库又名仓库，英文名repository
2. 创建一个版本库非常简单，首先，选择一个合适的地方，创建一个空目录
3. 命令把这个目录变成Git可以管理的仓库
        $git init

4. 告诉Git，把文件添加到暂存区
        $git add

5. 告诉Git，把文件从暂存区提交到本地仓库,并添加本次提交的说明
        $git commit -m "your description"

6. 命令可以让我们时刻掌握仓库当前的状态
        $git status

7. 可以查看修改内容
        $git diff

8. 命令显示从最近到最远的提交日志
        $git log

9. 添加改变的文件还有描述至本地仓库，新增的文件仍然要add。
        $git commit -a

*******

## 远程仓库
1. 本地关联远程库
        $git remote add origin git@github.com: account-name / repo-name.git

2. 查看已经关联的远程库
        $git remote -v

3. 删除远程仓库
        git remote rm repo-name

4. 本地关联远程后，往上push 总是失败，就是
        $git push  -u origin master
报错貌似不存在远程仓储。后来新建远程仓储把教程里图片第二个勾选上并选了选项，就是初始化Initialize this repository with a README  这里的。然后又push失败，不过这次是提示远程和本地不同步，然后执行
        git pull --rebase origin master
把远程的初始化文件readme取到本地，然后push成功。

5. 把本地库的内容推送到远程，用git push命令，实际上是把当前分支master推送到远程。由于远程库是空的，我们第一次推送master分支时，加上了-u参数，Git不但会把本地的master分支内容推送的远程新的master分支，还会把本地的master分支和远程的master分支关联起来，在以后的推送或者拉取时就可以简化命令。
        $git push -u origin master

6. 克隆一个仓库，首先必须知道仓库的地址，然后使用git clone命令克隆到本地当前的文件夹下。Git支持多种协议，默认的git://使用ssh，但也可以使用https等其他协议。使用https除了速度慢以外，还有个最大的麻烦是每次推送都必须输入口令，但是在某些只开放http端口的公司内部就无法使用ssh协议而只能用https。
        $git clone git@github.com: account-name / repo-name.git
******
## 分支管理

1.创建dev分支，然后切换到dev分支

          $git checkout -b dev
2.相当于1

    $git branch dev & git checkout dev
3.列出所有分支，当前分支前面会标一个*号

    $git branch
4.以切换回master分支

    $git checkout master
5.合并指定分支到当前分支

    $git merge dev
6.删除dev分支

    $git branch -d  dev
