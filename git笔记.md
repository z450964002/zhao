## git是什么
  + git是目前世界上最好的分布式版本管理器。
  + 版本系统就是能够记录每次的文件改动，可以回滚到之前的版本的神器。
  + git是linux觉得手动管理太麻烦，而且别人的还得要钱，于是他就自己用ｃ语言写了一个git。而且可以通过github社区免费使用。
+++++++++++++++++++++



## 集中式与分布式的区别
  + 集中式需要联网下才能工作，并且此方式十分慢，想要修改需要单独把要修改的东西下载到本机上，修改完成在上传回总服务器。
  + 分布式可以每个人都单独下个完整的库，并且通过ssh协议，下载速度很快。修改完成后，可以互相推送，彼此都能看到修改的内容。如果大家统一放在一个主机里，提供给大家修正，会更加方便。而且git的分支管理也是优秀。
++++++++++++++++++++++



## 安装git
  + 在ubuntu上安装git只需要输入命令：sudo apt-get install git 就可以直接完成。
  + 其他linux版本需要在git官网下载源码，然后解压，依次输入　`./config`  `make`  `sudo make install`
  + Mac OX x 安装是苹果的安装，方法一，通过homebrew安装git。
  + 从AppStore安装Xcode，Xcode集成了Git，不过默认没有安装，你需要运行Xcode，选择菜单“Xcode”->“Preferences”，在弹出窗口中找到“Downloads”，选择“Command Line Tools”，点“Install”就可以完成安装。
  + windows安装git，可以从git官网直接下载安装程序，默认选项安装。安装完成后，在开始菜单找到Git-->Git Bash, 会弹出个命令窗口，安装完成后，需要最后的设置，输入：git config --global user.name "Your Name"   git config --global user.email "email@example.com"
++++++++++++++++++++++



## 创建版本库
  + `mkdir name`    创建个本地目录，要选好合适的位置
  + `cd name`     　进入这个文件里
  + `git init`　  　把他初始化，变成可管理的仓库
  + 如果是windows最好不要用记事本写，可以下载notepad++代替。
  + `vim name.txt`          　写个文件
  + `git add name.txt`        添加到仓库缓存区里
  + `git commit -m "注释"`　　提交到当前分支里，留个注释
+++++++++++++++++++++++




## 版本回退
  + `git status` 　　查看仓库当前的状态，看看有什么没有处理的。
  + `git diff`       查看做了什么操作。
  + `git log`        会显示每一次的提交记录，　也可以用`--pretty=oneline可以简化信息`。
　+ `git reset --hard HEAD^`     可以回退到上一个版本，多个`^`就可以多退一次。
　+ `git reset --hard 版本号`　　可以跳转版本，比如回到最新的。
　+ `git reflog`     可以查看命令历史，在看要去哪个版本。
+++++++++++++++++++++




## 工作区和缓存区
　+ 工作区　就是电脑的本地文件，
　+ 版本库　是在工作区里的一个隐藏目录，是属于git的版本库。里面有着自动的第一个分支master。
　+ 要把每次的修改都通过add添加到暂存区，然后在commit提交上。
++++++++++++++++++++



##撤销修改
  + `git checkout -- readme.txt`  在提交前撤销 一定要加 --　否则会执行跳转分支的命令。
　+ 已经提交了add，在commit之前发现了问题，需要先回退版本:git reset HEAD readme.txt 回到新版本的文件，再用git status查看，已经来到了，没add之前的时候，这次在进行丢弃工作区操作。
+++++++++++++++++++

