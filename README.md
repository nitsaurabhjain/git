# GIT

### VCS
Version control System is an utility used to manage multiple versions of our files/programs. It also have many other features like below.
1. Multiple developer can work simulteniously
1. provides the utility to solve conflict. it may come when more then one member work simulteniously.
1. We can create a document for project
1. Compare diff version of files or program

### GIT Specific 
```
working area (all files)---- Staging Area  (tracking files)-------Repository (committed files)
```
[Interview Q/A][Q/A] 
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
$git clone <url> #if u already have a project
$git push -u <not required default> <where> <what>
$git push origin master
$git push origin feature_branch
$git show <commit_id>//show the changes made under perticular commit
$git show <commit_id> --name-only
$git remote add origin <url> # add/change the origin if we want to push/create to code in some other repository
$git branch -a //shows all branch
$git branch <branch name> // git branch feature1; create a new feature1 branch
$git checkout <branch name> # git chechout feature1 ; switch to newly created feature1 branch # or
$git branch -b <branch name> # git branch -b feature1; create a new branch and switch to newly created branch
$git branch -d  <branch name> # git branch -d feature1 ; delete a branch;(-D: for force delete
$git merge <branch name> # git merge feature1 ; merge the feature1 branch into current branch
$git rebase master. # adds all the changes from master branch into your branch and then add your changes on the top of those changes
$git status #show all untracked and staging area files.
$git add <file name> or  git add . # to add all untracked file/s in staging area
$git add -f <file name> # forecely add even it is in .gitignore file.
$git log # shows all commits
$git log --oneline # shows all commits in one line
$git log --oneline --all --decorate --graph
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
**git reset :-**  Undo all the changes from staging, and local repo. It's a dangerous command, thing twice before you use it since it also remove the commit history.
```
$git reset HEAD or <commit_id>// $git reset --mixed HEAD (default)
$git reset HEAD~1
$git reset HEAD~2
$git reset --soft HEAD //undo the changes from local repo but keeps the changes in staging area
$git reset --hard HEAD //undo the changes from local repo as weel as from staging area
$ git push origin master -f // To push the same into repo
```
**git revert:-** Undo changes made under any specific commit and make a new fresh commit. it's is good option because it does not affect the history.
```
git revert <commit number>
git push origin master -f
```

**Note:-** Remember `git revert ` revert the changes of specific commit but `git reset` revert the changes upto that commit. 
**Ex**: Say we have three consultative commit c1, c2, and c3 and if we reset to c2 ie `git reset c2` then c3 will also be deleted. but in case of `git revert` only c2 changes will be removed

### Git stash

### Git stash
```
$git stash //create a stash
$git stash push -m "feature1" //create a stash with comment
$git stash list //list out all stash
$git stash apply //switch to latest stash
$git stash apply 1  or $git stash apply stash stash@{0} //switch to specific
$git stash drop 1 //drop specific stash
$git stash clear //remove all stash
$git stash show  -p // p is option and used to show the content to show the contenct
```

 [Q/A]: <https://www.edureka.co/blog/interview-questions/git-interview-questions/>
 [Downlod GIT]: <http://git-scm.com>