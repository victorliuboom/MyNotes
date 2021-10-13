## 1-git init 创建命令
``` java
    //创建.git目录
    git init xxx
```

## 2-git clone 克隆命令
``` java
    //克隆远程仓库
    git clone xxx
```

## 3-git config 配置信息
``` java
    //修改本地用户配置信息
    git config --global user.name "xxxxxxx"
    git config --global user.email xxxx@163.com
```

## 4-git add 添加命令
``` java
    //添加文件到暂存区
    git add [files1] [files2]    git add xxx.xxx
    //添加文件夹到暂存区
    git add [dir]
    //添加当前目录下所有文件到暂存区
    git add .
```

## 5-git status 状态
``` java
    //查看当前项目是否有更改状态
    git status
    //-s查看简短的输出结果 AM代表文件有修改
    git status -s
```

## 6-git diff 查看改动
``` java
    //查看尚未缓存的改动
    git diff
    //查看已缓存的改动
    git diff --cached
    //查看已缓存的与未缓存的所有改动
    git diff HEAD
    //显示摘要而非整个
    git diff --stat
```

## 7-git commit 提交命令
``` java
    //提交暂存区到本地仓库中
    git commit -m [message]  git commit -m "xxxxx"
    //提交暂存区的指定文件到仓库中
    git commit [file1] [file2] ... -m [message]
    //-a 参数设置修改文件后不需要执行 git add 命令，直接来提交 -a代表add
    git commit -a
```

## 8-git reset  回退命令
``` java
    //回退所有内容到上一个版本
    git reset HEAD^ 

    //HEAD 说明：
    HEAD 表示当前版本
    HEAD^ 上一个版本
    HEAD^^ 上上一个版本
    HEAD^^^ 上上上一个版本
    以此类推...

    可以使用 ～数字表示
    HEAD~0 表示当前版本
    HEAD~1 上一个版本
    HEAD^2 上上一个版本
    HEAD^3 上上上一个版本
```

## 9-git rm 删除命令
``` java
    //将文件从暂存区和工作区中删除
    git rm xxxx
    //强行从暂存区和工作区中删除修改后的 runoob.txt 文件
    git rm -f runoob.txt 
 ```

## 10-git mv 移动命令
``` java
    //用于移动或重命名一个文件、目录或软连接
    git mv [file] [newfile]
    //如果新但文件名已经存在，但还是要重命名它，可以使用 -f 参数
    git mv -f [file] [newfile]
 ```

## 11-git 查看提交历史
``` java
    //查看历史提交记录
    git log
    //以列表形式查看指定文件的历史修改记录
    git blame <file>
 ```

## 12-git remote 远程仓库操作
``` java
    //显示所有远程仓库
    git remote -v
    //显示某个远程仓库的信息
    git remote show [remote]
    //添加远程版本库
    git remote add [shortname] [url]
    //删除远程仓库
    git remote rm name
    //修改仓库名
    git remote rename old_name new_name 
 ```

## 13-git fetch 远程获取代码库
``` java
    //从远端仓库提取数据并尝试合并到当前分支
    git merge
    //配置好了一个远程仓库，并且你想要提取更新的数据，你可以首先执行
    git fetch [alias]
    //将服务器上的任何更新（假设有人这时候推送到服务器了）合并到你的当前分支
    git merge [alias]/[branch]
 ```

## 14-git pull 拉取
``` java
    //从远端仓库提取数据并尝试合并到当前分支
    git pull <远程主机名> <远程分支名>:<本地分支名>
    //将远程主机 origin 的 master 分支拉取过来，与本地的 brantest 分支合并
    git pull origin master:brantest
 ```

## 14-git push 推送
``` java
    //从将本地的分支版本上传到远程并合并
    git push <远程主机名> <本地分支名>:<远程分支名>
    //如果本地分支名与远程分支名相同，则可以省略冒号
    git push <远程主机名> <本地分支名>
    //例子
    git push origin master
    git push origin master:master
    
    //如果本地版本与远程版本有差异，但又要强制推送可以使用 --force 参数
    git push --force origin master
    //删除主机的分支可以使用 --delete 参数，以下命令表示删除 origin 主机的 master 分支
    git push origin --delete master
 ```