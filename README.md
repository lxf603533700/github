# github
learning github

# github介绍
github是一款分布式代码版本管理软件，相对于svn,能够较好的防止单点故障导致的代码版本历史销毁。

# github结构
工作区（写代码  add命令）->暂存区（添加但未提交 commit命令）->本地库（存储历史版本）

# 代码托管中心
  ## 局域网
     gitlab
  ## 外网
    [码云](https://gitee.com)
    [github](https://github.com)

# 远程与本地交互
 ## 团队内部协作
 ![image](https://github.com/lxf603533700/github/blob/master/team.png)
 ## 跨团队协作
 ![image](https://github.com/lxf603533700/github/blob/master/teams.png)
# 创建本地库
  ## 初始化本地库
     git init
  ## 设置签名
     形式：用户名、email
     作用：区分不同开发人员
     级别范围：项目级别（对当前本地库有效）、系统用户级别（操作系统的用户范围）
     级别优先级： 二者都有时采用项目级别，二者必须存在一个
     命令：
        项目级别：   git config user.name ...
                    git config user.email ...
                    签名保存在 .git/config 
      系统用户级别： git config --global user.name ...
                    git config --global user.email ...
                    签名保存在 家目录/.gitconfig 
