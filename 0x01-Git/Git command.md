sudo apt-get install git
ALL command :
     git remote add orijin link  
0_ normal command .
		    git init : create repo from command line 
		    git remote add origin https//... to add repo after init 
		    git status : status of file 
            git add . or 
            git reset name-file : add or delete from stage
                    git reset HEAD all unstage 
                    restore git restore --staged name of file 
            git commit -m "message" : commit files
            git push remote branch
            git push -u remote branch pull and push 
            git pull remote branch
            git clone link https with token // token github.com
            git remote -v : show me my remote 
                    Resetting the head clean command :
                         git clean -n show me file delete from working dir 
                         git clean -f delete file from working dir
                                if don't want to delete add it to stage 
1_ git config :
        git help config : all help of confiq
        git config -l --show-origin
        git config --list : to list configuration git
        make config :
               git config --global user.name "usr.name"
               git config --global user.email "usr.email" 
  git checkout :  ( )
         git checkout ID_commit name file : delete change and commit again
2_  LOG  and Revert  and reset ( show and delete commit ): 
      head is pointor to last commit .
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
3_ branch :
            git branch : show branch 
            git branch name new file create branch 
            git branch -m rename branch 
            git branch -d delete branch with no cpmmit 
            git branch -D delete branch with commit 
            git checkout n-b : change branch
            git checkout -b name of branch want to create and change 
            git merge branch _2 need to return to origin 
4_ stash ( hidden file ) //default last one// 
           git stash show : give me all file and change i have on stash 
            git stash : is stage area
                        git stash save "comment" to add comment 
            git stash list : stash{0}
            git stash pop : dropt file last one by default
                    or git stash pop stash@{n-s i want to dropt and give me file} 
             git stash drop to delete stash without give me file 
            git stash apply : take file and don't dropt stash last one
            git stash clear : delete all stash 
5_ gitignore  
     there is some file we don't want to upload to github 
             like .DS_Store for i Macs
            like thumbs.db
      or something else ...
       command :
            touch .gitignore create this file and enter with vi or emacs write
          * write name of file 
          * or can use * to ignore a lot of file ignore one use !name of file 
                 example : 
                       * *.log
                        !vip.log
                        ignore all file ended by .log  but dont ignore vip.log
            *git ignore patterns* *search for it 
6_ Tagging and relesing :
