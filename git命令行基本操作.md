## 配置git
1. git config --global user.name "name"
2. git config --global user.email "email-address"
3. (...还可以配置更多)
4. git config --list     //查看当前所有配置项
5. git                   //查看所有命令行

## 创建git仓库
1. git init              //将已创建的文件夹作为仓库
2. git init xxx(文件夹名) //新创建文件夹并作为git仓库
3. git clone xxx(github地址 eg:https://github.com/Liuszzz/Liuszzz.github.io.git) //直接克隆远程仓库

## 基本用法
1. git status            //查看git仓库下文件动态
2. git add .             //将当前目录下所有修改添加至暂存区(保存)
3. git add xxx(文件名)    //添加指定文件到暂存区
4. git commit -m "对文件的描述" //给当前提交节点一个描述(提交暂存区并添加描述)
5. git log               //查看版本记录
6. git log -p            //查看文件具体改动
7. git checkout xxx(commit的节点代码) //回溯到指定的历史节点
8. git checkout -        //回到上一个节点

## 三种状态
1. modified  //已修改
2. staged    //已暂存
3. committed //已提交

获取的Git仓库中的所有文件都是committed状态。
如果你在本地修改了文件a，a的状态就变成modified的；
如果使用git add a，a的状态变成staged；
如果使用git commit，a的状态就变成commited。
当然还有一种文件状态，未跟踪状态（unversioned/untracked）。
通过使用git add可以把未跟踪状态变更为staged；
通过git rm可以将staged或者committed状态变为未跟踪状态。

## 标签tag
1. git tag           //显示当前库中的标签
2. git tag -a 标签名 -m "备注" //附注标签
3. git tag -a 标签名 -m "备注" xxx(节点代码) //指定节点创建标签
4. git show 标签名    //查看某个标签的详细信息
5. git checkout 标签名        //到标签所在的提交版本

## 分支branch
1. git branch 分支名
2. git checkout 分支名        //回到指定分支
3. git checkout -b 分支名     //创建并切换至分支
4. git log --all --graph     //图示全部历史记录

## 合并分支
1. git merge 分支名           //合并分支到当前分支
2. git branch -d 分支名       //删除分支。
如果合并时存在冲突(conflict)，需要手工修改

## 远程仓库
1. git remote add 远程名称 远程地址  //添加远程仓库
2. git remote               //列出所有远程仓库
3. git push -u 远程名 分支名        //上传代码,默认使用远程名origin和分支名master,上传之前需要add和commit
4. git pull                         //下拉更新
