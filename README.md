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
  
  第一步：创建本地库
  
  第二步：创建远程库
  
  第三步：将本地库推送到远程库【push】
      
      0.查看远程库地址
      
       git remote -v
      
      1.配置远程库地址
       
       git remote add origin 远程库地址
      
      2.推送  
      
       git push origin 分支名 
  
  第四步：克隆操作
      
      git clone 远程库地址
      
      克隆后，完整的将远程库下载到本地、创建origin远程地址、初始化本地库
  
    第五步：邀请用户加入团队，用户接受
  
    第六步：用户提交代码
      
      1.提交到本地库
      
      2.push到远程库 git push origin 分支名 
  
    第七步：抓取到本地
        
        git fetch [远程库地址别名][远程库名]
        
    第八步：合并操作
  
         git merge [远程库地址别名][远程库名]
         
    综合七、八步：
   
     git pull [远程库地址别名][远程库名]
  
    第九步：解决冲突
      
      【方法见分支冲突】
    
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

# 操作命令

## 查看状态
    
    git status

## 添加到暂存区
   
    git add 文件名（或*）

## 撤出暂存区
   
    git rm --cached 文件名（或*）
    
## 提交到库
    
    git commit  -m '备注，操作记录' 文件名（或*）
    
## 查看历史记录操作
    
    git log
    
    git log --pretty = oneline
    
    git log --oneline
    
    git reflog 
    
## 版本前进或后退

### 基于索引值[HEAD]
    git reset --hard 索引值

### 基于 ^ 符号（只能后退）
    
    git reset --hard HEAD^
    
    注： 一个 ^ 表示后退一步 多个表示多步

### 基于 ~ 符号（只能后退）
    
    git reset --hard HEAD~n
    
    注：n表示后退n步

### reset命令三个参数对比
    
    --solf 仅仅在本地库移动HEAD指针
    
    --mixed 移动本地库HEAD指针 且 重置暂存区
    
    --hard  移动本地库HEAD指针 且 重置暂存区 且重置工作区

## 删除文件并找回

### 方法一 版本回退
    
    git reset --hard 文件存在的索引值
    
### 删除文件在暂存区中
    
    git reset --hard HEAD
    
## 文件比较
    
    【工作区文件域暂存区文件进行比较】
    git diff 文件名   
    
    【将工作区中的文件域本地库历史记录进行比较】
    git diff HEAD 文件名  
    
    注：不带文件名 表示比较多个文件
    
 # 分支管理
 
 ## 分支操作
   
   ### 查看所有分支
     
     git branch -v
      
   ### 创建分支
     
     git branch 分支名
   
   ### 切换分支
      
      git checkout 分支名
      
   ### 合并分支
       
       第一步：git checkout 被合并的分支名 【切换到接收修改的分支上】
       
       第二步：git merge 有新内容的分支名 
   
   ### 解决冲突
      
      产生冲突原因：两个分支同时修改了同一个文件的同一个位置 合并时产生冲突
      
      解决：修改文件内容-> git add 文件名 -> git commit [不用带文件名] 
