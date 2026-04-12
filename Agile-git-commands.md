Agile

Assignment 1.



**to push code** :

git config --global user.name Monish-vit

git config --global user.email monishwar.2023@vitstudent.ac.in

git init

git add .

git commit -m "message"

git status



**to push code method 2: from locally**

git init 

git add .

git commit -m "message"

git branch -M main

git remote origin https://github.com/

git push -u origin main -- for remote



**to modify and stage and commit changes:**

git diff

git add .

git commit -m "msg"

git log --oneline

git push -u origin main   -- for remote



**add new branch and switch between them**

git branch <name>

git checkout <name>

git add .

git commit -m "message"

git push -u origin <name>  -- for remote

git checkout master

git checkout <name>



**merge branch to main**

git checkout master

git merge <name>

git log --oneline



**working in remote repo - create,add,push**

git remote add origin <paste link>

git remote -v 
(shows list of remote repo linked to proj)





**discard uncommitted changes**

git status

git restore <name.py>

git status





**merge conflicts - merge,resolve conflict,commit resolved**



git checkout -b <feature name> (same as create branch and checkout)

(this creates new branch and changes to it)



git commit -a -m "message" ( this stages and commits only modified files not new files) (for new files add .)



git checkout master

git commit -a -m "master changed"

git merge <name>

git add <file>

git commit -m "resolved"







**ignore file and ignore patterns**

.gitignore file 



code .gitignore

New-Item test.log

git status



or else create file in vs

git status

git add .gitignore

git commit -m "added .gitignore"

git push





**fetch latest change, pull update, resolve conflict**

git fetch (origin)

git pull origin main







**review commit history, push final, prepare release version**



git log --oneline --graph --all

git tag -a v1.0 -m "final"

git tag

git push origin master

git push origin --tags





**General:**



git --version

git config --global user.name "name"

git config --global user.email email@gmail.com

git init (creates a git repo)

git clone <repo link>

git status

git add .

git add file.py

git commit -m "msg"

git commit --amend (modify prev command)

git log

git log --oneline

git log --oneline --graph --all

git branch (lists names)

git branch <name>

git checkout <name>

git checkout -b <name> 

git merge <branch>



git remote add origin <url>

git remote -v

git push origin main

git push -u origin main

git pull origin main (fetch and merge)

git fetch



git restore file.txt

git restore --staged file.txt (unstages)

git reset --soft HEAD\~1  (undo commit,keep staged)

git reset --mixed HEAD\~1 (undo commit, keep changes)

git reset --hard HEAD\~1 (undo commit, delete changes)

git revert <commit-id> (creates reverse commit)



**stash -- save temp**

git stash (saves work temp)

git stash list (show all stashes)

git stash apply (applies each)

git stash pop (applies, removes stash)



**tagging**

git tag v1.0

git push origin v1.0





git diff

git diff --staged



