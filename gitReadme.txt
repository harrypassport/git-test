1. 下载 git https://git-scm.com/download
2. git config --global user.name 'xxx'
   git config --global user.email 'xxx'
   查询
   git config user.name 
   git config user.email 

3. 长命令别名
   touch ~/.bashrc
	alias git-log='git log --pretty=oneline --all --graph --abbrev-comm'
	alias ll='ls -al'
   解决bash 乱码问题:
	git config --global core.quotepath false  
   	($git/etc/bash/bashrc 文件后加两行:
		export Lang='zh_cn.UTF-8'
		export LC_ALL='zh_cn.UTF-8'
4. 创建本地仓库
   进入本地目录 
   git init     (出现.git 表示本地仓库创建了)
5. 状态： git status
	未跟踪: workplace area                          状态变为 untracked (使用git add) 
        ->
        未暂存: index area (git add .)			状态变为 Stage (使用git commot -m 'message') 
	->
	已暂存: repositry (git commit -m 'notes ...')   状态变为 unmodified (如果使用git rm 又变回workplacearea  modified)
    查看
        git log
6. 版本退回  (可查看CommID: git reflog)
    git reset --hard commitID
7. .gitignore 中文件不需要add 提交

8. 分支与合并
   git branch 查看分支
   git branch xxxx 创建 xxxx分支
   git checkout xxxx 切换到某分支
   git checkout -b xxxx 创建并切换到 xxxx分支 
   git branch -d xxxx 删除分支 或 git branch -D xxxx 强行删除分支 （删除时，常切换到别的分支）

   git merge xxxx 合并分支 xxxx 到当前分支上

9. 分支使用原则与规范
   master <-> develop <-> feature（可删除）
      debug->(develop,master)

10. 远程仓库托管：github/码云gitee/gitlab(公司层面）
    国内一般使用gitee， 创建的时候，其他选项不用选
    配置SSH 公私钥对已以进行本地远程推送
    1.  ssh-keygen -t rsa (非对称密钥，一路回车。。如果存在自动覆盖）
    2.  cat ~/.ssh/id_rsa.pub  查看后复制到gitee 用户设置下面的SSH 公钥
    3.  ssh -T git@gitee.com  本地确认

    4. git remote add origin git@gitee.com:XXXX/yyyy.git   （通常远程仓库名称取origin）
    5  git remote  查看远程仓库名
    6  git push origin master：remotemaster   将本地仓库分支 master 推送到 远程, 如果远程分支一样则
       git push origin master   将本地仓库分支 master 推送到 远程, 如果远程分支一样则

       git push -f --set-upstream origin master:remotemaster    -f 表示强制 --set-upstream 表示建立本地分支和远程对应关系
       git push (在建立与远程绑定关系后可以直接使用git push)
       git branch -vv  （查看本地远程分支的的绑定关系）

    7. git clone git@gitee.com:XXXX/yyyy.git  'test文件夹'
    8. git fetch origin master  (抓取远程分支到本地当前分支，但不执行合并）
    9. git pull origin master  (抓取远程分支到本地当前分支，并执行合并=git fetch +merge）


      


 
	



 	    

     
	
    
