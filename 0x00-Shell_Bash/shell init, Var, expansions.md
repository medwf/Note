[medium.com/@sankad_19852/shell-scripting-exercises-5eb7220c2252](https://medium.com/@sankad_19852/shell-scripting-exercises-5eb7220c2252)
## Expression 
/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin
echo $((2 + 2)) ====> print 4 
echo $(($((5**2)) * 3)) ==> print 75
echo Five divided by two equals $((5/2)) 
       Five divided by two equals 2
echo with $((5%2)) left over.
        with 1 left over
echo front -{A-B-C}-back A or  B or  C
       front-A-back  front-B-back front-C-back
echo Number_{1..5} from 1 to 5 
       Number1 Number2 ... Number5
echo {Z..A} from Z to A
       Z Y X W ... C B A
echo a{A{1,2},B{3,4}}b
       aA1b aA2b aB3b aB4b 
mkdir {2017..2019}-{01..12}
      2017-01 2017-07 2018-01 2018-07 2019-01 2019-07 2017-02 2017-08 2018-02 2018-08 2019-02 2019-08 2017-03 2017-09 2018-03 2018-09 2019-03 2019-09 2017-04 2017-10 2018-04 2018-10 2019-04 2019-10 2017-05 2017-11 2018-05 2018-11 2019-05 2019-11 2017-06 2017-12 2018-06 2018-12 2019-06 2019-12

### Parameter Expansion
echo $USER
      root 
env or printenv to print variable 

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

