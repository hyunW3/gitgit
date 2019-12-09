# gitgit
document for git

# How to commit the git

1. git init 
2. git config --global user.name "hyunW3"
3. git config --global user.email "0176778602@naver.com"
4. git add [something]
5. git commit -m " [ recode the message ]
6. git remote add origin "https://github.com/hyunW3/~ ... "

6-1 git remote -v   local repo connect to remote repo

7. git pull # in local
  git pull origin master # at first
  Or you could set it up so that your local master branch tracks github master branch as an upstream:
  git branch --set-upstream-to=origin/master master
  git pull
  This branch tracking is set up for you automatically when you clone a repository (for the default branch only), but if you add a remote   to an existing repository you have to set up the tracking yourself. Thankfully, the advice given by git makes that pretty easy to         remember how to do
  
    7-2. git pull 시 error = fatal: refusing to merge unrelated histories
    -> git pull origin [branchname] --allow-unrelated-histories
8.  git push origin master # to the web 

# temperary not asking 
1-1. git config credential.helper store -> almost perment
1-2. git config credential.helper 'cache --timeout=360' -> default min:15
--global 옵션으로 모든 git 활동에서 저장된 정보 이용

links : https://rogerdudler.github.io/git-guide/index.ko.html

#Problem 
1. waring: CRLF will be replaced by LF in ... [unix OS user]
  or LF will be replaced by CRLF in ..  [window user]
  
  Solution: enable "core.autocrlf"
  As window user 
    git config --global(optional) core.autocrlf true
  AS linux or Mac
    git config --global(optional) core.autocrlf true input (input은 단방향을 의미)
index : https://blog.jaeyoon.io/2018/01/git-crlf.html
