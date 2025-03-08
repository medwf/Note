# Installation.
- sudo apt install git
# Command.
## Initialized project.
- `git init` : create repo from command line 
- `git remote add origin https//`: ... to add repo after initialized.

## See Changes Current Directory.
- `git status` : status of file 

## Stage.
- `git add .` : add all change to stage.
- `git add fileName`: add file to stage.
- `git reset name-file` : delete from stage
	- `git reset HEAD`:  all un stage.
	- `git restore --staged name of file` 

## Commit.
- `git commit -m "message"` : commit changes with message.

## Push/Pull change to Remote Repository.
- `git push remote branch` : push commit to remote repository.
- `git push -u remote branch`: pull all changes in remote repo and push your changes. 
- `git pull remote branch `:  get all changes in remote repo. 
- `git clone link-https` clone repo to your device.
- `git remote -v` : show me my remote 
-         Resetting the head clean command :
-              git clean -n show me file delete from working dir 
-              git clean -f delete file from working dir
-                     if don't want to delete add it to stage 
# Git config.
- `git help config` : all help of configure.
- `git config -l --show-origin`
- `git config --list` : to list configuration git.
- Make config :
	- `git config --global user.name "usr.name"`
	- `git config --global user.email "usr.email"` 

# Git checkout.
- `git checkout ID_commit name file` : delete change and commit again
## LOG  and Revert  and reset ( show and delete commit ): 
      head is pointer to last commit .
          log command : 
                git help log : get help .
                git log All commit i did 
                     commit hash (HEAD -> branch , remote/branch)
                git log -n x  : last x commit
                git log --oneline : give short me commit  with ID code 
                git log -p name of file : to know all commit about one file  
         Revert command ( unstage commit ) :
                git revert ID_COMMIT 
                git revert ID_COMMIT name_of_file ( to delete change for commit exactly n_f)
        reset command :
                   git reset ID_commit to (delete or return commit) 
                        git reset --hard hash id   ( delete all commit  and change  )
                        git reset --soft hash or id ( delete commit and keep change but still on stage )
                        git resrt --mixed ( delete commit save change but not staging )
                   to delete multi commit need to take hash of last commit 
                                    change head and delete commit 
                                    next step : git push remote branch --force 
# branch :
            git branch : show branch 
            git branch name new file create branch 
            git branch -m rename branch 
            git branch -d delete branch with no cpmmit 
            git branch -D delete branch with commit 
            git checkout n-b : change branch
            git checkout -b name of branch want to create and change 
            git merge branch _2 need to return to origin 

# stash ( hidden file ) //default last one// 
           git stash show : give me all file and change i have on stash 
            git stash : is stage area
                        git stash save "comment" to add comment 
            git stash list : stash{0}
            git stash pop : dropt file last one by default
                    or git stash pop stash@{n-s i want to dropt and give me file} 
             git stash drop to delete stash without give me file 
            git stash apply : take file and don't dropt stash last one
            git stash clear : delete all stash 
# .gitignore  file
- There is some file we don't want to upload to GitHub. 
	- like .DS_Store for i Macs
    - like thumbs.db
    -  Can use `*` to ignore a lot of file ignore one use !name of file Example : 
        -  *.log, !vip.log
        - ignore all file ended by .log  but don't ignore vip.log
		- git ignore patterns search for it

