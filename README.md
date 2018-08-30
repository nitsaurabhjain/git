# GIT

### VCS
Version control System is an utility used to manage multiple versions of our files/programs. It also have many other features like below.
1. Make us aware from the merge conflict and solve it also.
1. It allows us to merge the code when more then 1 team member is working on a project.
1. Create a document.
1. We can create a document for project

### GIT Specific 
```
working directory (all files)---- Staging Area  (tracking files)-------Repository (committed files)
```
[downlod git from here][Downlod GIT] , install and do the below config

### Initial Configuration
```git
$ git config --global user.name "Saurabh Jain"
$ git config --global user.email "saurabh.manit.jain@gmail.com"
$ git config --global core.editor "'C:/Program Files (x86)/Notepad++/notepad++.exe' -multiInst -nosession"
$ git config --global http.proxy "http://proxy.us.oracle.com:80"
```
### List out Configuration
`git config --list`
### Remove Configuration
$ git config --global --unset http.proxy
#### Create git project
`$git init`
* README.md (md - Mark down)
* .gitignore : holds all the file/folder names which we don't want to check-in in VCS

### IMP GIT commands
```
$git help <command name>
$git show <commit_id>//show the changes made under perticular commit
$git status #show all untracked and staging area files.
$git add <file name> or  git add . # to add all untracked file/s in staging area
$git log # shows all commits
$git log --oneline # shows all commits in one line
$git diff   or git diff <file name> # git diff compare the local files from staging area file
$git diff HEAD <file name>  # compare the local files from repository
$git diff HEAD~1 <file name>  # compare the local files from repository
$git diff --staged # compare staged file/s from last commited file/s
$git diff <commit number> # ie git diff 6d6afa1 -  get it from git log --oneline
$git commit -m "message"
$git commit  # dont add -m 'message' to add multiline commit 
```
### Undo changes.
**git checkout:-**  remove the changes from working dir only
```
$git checkout <file> or git checkout .
```
**git reset :-**  Undo all the changes from staging, and local repo and keep those files in working area. dangerous command thing twice before use since it also remove the commit history.
```
$git reset HEAD or <commit_id>// $git reset --mixed HEAD (default)
$git reset HEAD~1
$git reset HEAD~2
$git rest --soft HEAD //undo the changes from local repo but keeps the changes in staging area
$git rest --hard HEAD //undo the changes from local repo as weel as from staging area
```
**git revert:-** Undo changes made under any specific commit and make a new fresh commit. it's is good option because it does not affect the history.
```
git revert <commit number>
```
 [Downlod GIT]: <http://git-scm.com>