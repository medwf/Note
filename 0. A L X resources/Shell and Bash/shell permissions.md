- `chmod`- modify file access rights
        r w x : read write execute (owner, group, others)
        d, - , l : directory , file , 
    Numeric mode: (octal value)
               r : 4 , w : 2 , x : 1
              chmod NNN name of file 
    symbolic mode : 
             syntax : chmod reference operator mode file
             reference u : owner of the file 
                             g : users who are member of g
                             o : user who are mmbr of other
                             a: all ugo
                operator  + : add mode to specified classe
                                -:  remove mode 
                                =: exact mode to specified class
                mode       r , w , x 
                chmod ug+x,o+r hello ( 2 command )
                reference : 
                        chmod --reference=RFILE n f
- `sudo` - temporarily become the superuser
         sudo -i to go super user and root file 
- `su` - temporarily become the superuser
- `chown` - change file ownership
        chown owner:group some_file
        chown -R owner:group dir 
        chown 500 name_of_file
                Change the owner to user identifier "500" for the file
         -h : effect symbolic link 
         if : 
         --from=currant_owner:currant_group n_owner:n_group name of file 
- `chgrp` - change a file's group ownership
- `id` - 
- `groups`- list group
- `whoami`- user or owner 
- `adduser`- 
- `useradd` - 
        sudo useradd new_name_user
- `addgroup`- 
         sudo groupadd new_name_user