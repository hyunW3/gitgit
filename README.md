# gitgit
document for git

# How to commit the git

1. git init 
2. git config --global user.name "name"
3. git config --global user.email "tour email"
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
해당 기록 삭제 : git config --local --unset credential.helper 

# restore the git commit
1. git log (to find log data)
2. git reset --hard (your commit log, ex)64a0de...)
또는 git reset HEAD^ (한번 뒤로) / HEAD^^ (두번 뒤로) 사용하자

# git reset 취소
1. git reflog
2. git reset --hard HEAD@{이동하고 싶은 번호}


links : https://rogerdudler.github.io/git-guide/index.ko.html

# over 100MB commit cancel
커밋전에 .gitignore 설정 잘하자! 
https://rtyley.github.io/bfg-repo-cleaner/
1. jar file 다운받고 / java를 설치한다
2. 해당 repo 에서 java -jar bfg-1.13.0.jar(버전 맞추어서) --strip-blobs-bigger-than 100M
3. git repack && git gc (에러 발생시)
4. git push 하면 된다.


출처: https://vateran.tistory.com/51 [BrainDump]

# make tree project 
(ex project A include subproject B,C)
   A
 /  \
 B   C
 1. make repo of A, then connect to github repo
 2. git subtree add --prefix=[name] [github url of B,C each]
 3. then pull & push

#Question
git commit, git checkout, git merge

#Problem 
1. waring: CRLF will be replaced by LF in ... [unix OS user]
  or LF will be replaced by CRLF in ..  [window user]
  
  Solution: enable "core.autocrlf"
  As window user 
    git config --global(optional) core.autocrlf true
  AS linux or Mac
    git config --global(optional) core.autocrlf true input (input은 단방향을 의미)
index : https://blog.jaeyoon.io/2018/01/git-crlf.html


