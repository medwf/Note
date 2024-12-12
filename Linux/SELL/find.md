Search for files in a directory:

- Command: find  [directory…] cuitenes  expression action.
-  -name : name file.  \? Save expression .

- To protected exp write a name on "" or ''

- -type : type file. (f:file|l:symbolic link| c: char| d: directory | b: block | )
- -perm : permeation.

- -perm mode 

- Min has -mode. /mode ou operation . Owner || group || other.

- -links +- n : n = n , -n = n < n , n > n .

- -link +5  how many link in file or directory.

- -user  <name user> : search file that have name file .
- -group <name group> : search  file has that name group.
- -nouser || -nogroup : file that has no user or group.
- -size : +-n : search file has size unity block = 512 octets. N = number block = nB.
- N on character nc. C = bytes
- 10o < f < 12o : -size 10c -size -12c .
- -inum : same number node. Hard link.

- -inum numberNode

- -atime
- -mtime
- -clime

- -empty : empty file. Or directory.

- (a|m|c)min :

- Always true :
- -print  : print file found.
- -ls : option like command ls.

Example :  find A/  -type f -name '?'  -print  

     t/f &&  t/f  &&  t

AND exp : find exp exp exp== find exp -and exp -and exp == find exp -a exp -a exp

OR exp: == find exp -or exp -or exp == find exp -o exp -o exp

Not exp : not expression === -not exp  === ! exp

find exp -o exp -a exp : -a execute first.

force execute with '('')' as condition.

Action :

- -exec : execute command
- -exec cmd \{\} ; is command exec true else false.
- -ok ask for permeation execute command

User :

- Delete user : userdel nameUser.
- Userdel -r nameUser : delete User and files.
- -u : uid => useradd -u 500 nameUser