## [GitHub](https://github.com/formerlyhj) [gitbook](https://www.git-scm.com/book/zh/v2)   

### <font color=red> git简单笔记   </font>
- git init  （初始化仓库）
- git add + filesname（加入跟踪文件，add .跟踪当前文件加所有文件）
- git commit -am ‘txt’（提交修改）
- git status （查看文件当前状态）
- git checkout 加分支  （切换分支）
- git remote add 名字 地址  （打包分支）
- git push 名字 分支  （推送分支） 
- git remote -v  （查看远程仓库） 
- git clone [url]（克隆远程仓库） 
- git merge+分支 （合并分支）
- git rm --cached README（取消文件跟踪）
- git log -p -2  (查看近两次提交的差异)
- git branch testing（仅新建不切换） 
- ps -ef|grep * (查看进程) 
- mkdir + 文件名（创建文件夹）
- touch + 文件名（创建文件）
- vim + 文件名（进入编辑模式）

# 本地

- git branch 查看分支all/-a远程和本地
- git ls-files 查看跟踪文件，add . 添加的文件夹回向下跟踪每个文件
- git rm --cached+文件 取消文件跟踪，加一个-r是取消对文件夹的跟踪，递归原则
- git branch -- delete+分支  删除本地分支
- git remote remove +推送命名 。取消本地与服务器端的推送关联  
 
# 远程服务器  
- git push ‘test’ -- delete+分支。删除远程分支
- git remote show +‘test’。展示远程库
