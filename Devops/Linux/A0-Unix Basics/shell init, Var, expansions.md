### Command Substitution
echo $(ls)
      list all life in working directory 
ls -l $(which cp)
       -rwxr-xr-x 1 root root 71516 2007-12-05 08:58 /bin/cp
file $(ls /usr/bin/* | grep bin/zip)
ls -l \`which cp\`  It uses back-quotes instead of the dollar sign and parentheses 

### Quoting : problem expansion  
echo this is a     test 
      this is a test
echo The total is $100.00
      The total is 00.00
       The total is 00.00
       
## Double Quotes 
The first type of quoting we will look at is double quotes. If we place text inside double quotes, all the special characters used by the shell lose their special meaning and are treated as ordinary characters. The exceptions are “$”, “\” (backslash), and “\`” (back- quote).
ex : 
- ls -l "two words.txt" : By using double quotes, we can stop the word-splitting and get the desired result
- echo "$USER $((2+2)) $(cal)"
         me 4 
         February 2020 
         Su Mo Tu We Th Fr Sa 
                                       1 2
         3    4     5   6    7  8   9 
        10 11 12 13   14  15 16
        17 18 19 20 21 22 23
         24 25 26 27 28 29
- echo "this is a     test"
       this is a     test 

## Single Quotes
$ echo text ~/*.txt {a,b} $(echo foo) $((2+2)) $USER
      text /home/me/ls-output.txt a b foo 4 me 
$ echo "text ~/\*.txt {a,b} $(echo foo) $((2+2)) \$USER"
        text ~/*.txt {a,b} foo 4 me
$ echo 'text ~/*.txt {a,b} $(echo foo) $((2+2)) $USER' 
        text ~/*.txt {a,b} $(echo foo) $((2+2)) $USER

## Escaping Characters
echo "The balance for user $USER is: \\$5.00" 
       using backslash to escape character
- \\a
- \\t : make tab 
- \\n : new line
- \\f : 
- \\ : insert backslash

