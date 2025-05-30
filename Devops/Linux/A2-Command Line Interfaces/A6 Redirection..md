- `ls > file` : redirected list file to file(over written).

- `cat < file` : list contents file.
- `sort < file_list.txt` : redirection contents file to sort command 
- `sort < file_list.txt > sorted_file_list.txt` : redirected input to sort command after that redirected to output of sorted.

- `cat << Tiquet` : read from input to end with `Tiquet`
- `cat << fin > file` : read from input to fin and redirection to file 
- `ls >> file_list.txt` : redirected list file (appended)

- `2>` (error redirection): This operator redirects the standard error output of a command to a file 
- `2>>` (error redirection with append): This operator appends the standard error output of a command to a file. If the file doesn't exist, it creates a new file
- 
- `&>` (combined output and error redirection): This operator redirects both standard output and standard error of a command to a file
- `&>>` (combined output and error redirection with append): This operator appends both standard output and standard error of a command to a file.

- `/dev/null` : It is a special file in Linux that discards any data written to it and produces no output when read from. You can use it for redirecting output that you don't want or need.
- `cmd <<< str` (here-string): This operator allows you to pass a string as the input to a command
- `(command1; command2) > file`" (command grouping): You can use parentheses to group commands and redirect their output collectively

## Filters
`Filters` : take standard input and perform an operation upon it and send the results to standard output .
- sort : sort lines of text files (A_Z a_z 0_9 ).
    -r :  reverse the result of comparisons
    -R : random 
    -o : sort file1 file2  sort file2 Ver file1( save change f1)
    -n : To sort  a file numerically .
    -nr : To sort a file with numeric data in reverse order
    -k n : option to sort on a certain column n 
- echo : 
       1. Displaying messages: The echo command can be used to display messages or information on the console or in a text file. This is useful for providing feedback to the user, displaying error messages, or providing instructions.
       2. Displaying variables: Batch scripts often use variables to store information or data. The echo command can be used to display the value of a variable on the console or in a text file, making it easier to debug and troubleshoot scripts.
    3. Debugging: The echo command can be used to debug scripts by displaying the values of variables, commands, or system information. This can help identify errors and improve the efficiency of scripts.
     4. File output: The echo command can be used to redirect output to a file, making it easier to save and share information. This can be particularly useful when generating reports or logs.
     5. Script automation: Batch scripts can automate repetitive tasks, making them more efficient and less prone to human error. The echo command can be used to provide feedback and ensure that scripts are running as expected.
- cat multi file : 
    - -n display with number 
    - cat > file create file and write somethings and exit 
    - cat copy cent 1 > to cent file 2 overwritten 
    - cat file1 >> file2 will append the contents 
    - tac file " reverse display content file "
    - cat -E "filename" Will highlight the end of line with "$"
    - cat -A  "filename" **writing** -vET
    - cat -- "-dashfile" Display dashfile 
    - cat "file1" "file2" "file3" > "merged_filename" will merge content of 3 or more file to new file 

- tail : default display 10 line down 
     - -n -Num : Display last n line .
     - +n : display start from n to last line 
     - -c n oe -n : Display last n character 
     - -c +n : Display start from n character to the end 
     - -q :  It is used if more than 1 file is given. Because of this  command, data from each file is not precedes by its  file name. ( delete ==> file <== ).
     - -v : By using this option, data from the specified file is always preceded by its file name ==> file <==
     -  **cat state.txt | head -n 20 | tail -n 5  > list.txt**
         display last 5 from 20 first live and write them in list.txt
    - 
- find : 
    - find dir -name sample.txt
    - find . \-type f \-name *.js \-delete to delete file 
    - find dir -name .txt find all file end with .txt in GFG
    - find dir -name sample.txt -exec rm -i {} \;
         find and delete option with confirmation 
    - find dir -empty : search for empty files or directory
    - find dir -perm 664
    - find dir -type f -name "*.txt"
- wc : print number of lines and n of word and size
    -l : display just number of lines 
    -w : display just number of words 
    -c : display size of alx 
    ls gfg | wc -l : print number of file in working directory 
- uniq : remove all repeated lines in a file.
     -  uniq option input-file  output-file
     - uniq -c file how many time line repeated
          1 mohamed
          4 alx
          2 soft
     - uniq -d file : find repeated lines
          alx 
          soft
    - uniq -u file new file : Finding lines which are unique and store in another file
            when chat new file that will display  mohamed
- grep 
    - grep "word" file ( print word from file )
    -   grep from [a-z] 
    - grep -f file file  
    - grep -A N "word" find word and print n line num after that 
    -  grep -B N "word"  find word and print n line num after that
    - grep -v "word" select no matching file 
- tr : change text 
    -  cat file | tr a-z A-Z or 
         cat greekfile | tr :lower: :upper:
          tr :lower: :upper: < file
    -  echo "Welcome To GeeksforGeeks" | tr [:space:] "\t"
        tr [:space:] "\t" <<< "Welcome To GeeksforGeeks"
            Welcome      To      GeeksforGeeks 
    - tr "{}" "()" < file   >newfile.txt
            change {ddd} to [ddd] and write it in newfile
    - -s : delete space  echo "Welcome    To    GeeksforGeeks" | tr -s " "
            tr -s " " <<< "Welcome    To    GeeksforGeeks"
            Welcome To GeeksforGeeks
    - -d delete word  : echo "Welcome To GeeksforGeeks" | tr -d W
            delete w . 
            tr -d [:digit:] <<< "my ID is 73535"
            echo "my ID is 73535" | tr -d [:digit:]
            my ID is 7869876 
    - 
- rev : reverse the lines characterwise
      rev mohamed
            demahom
            xla
            tfos
- cut : cut OPTION... FILE... : 
    -   cut -b 1,3 file  ( 1 and 3 character )( cut by byte)
                cut -b -3 file ( print 3 first character )
                cut -b 1-3,5-7 file ( from 1 to 3 and from 5 to 7)
                In this, 1- indicate from 1st byte to end byte of a line
                cut -b 1- file
         - cut -c 2,5,7 file ( cut by character )
                cut -c 1-7 file 
                cut -c -5 file 
          - cut -d "x" -f N file :  for d what yoy want to cut for 
             for f what you want to cut 
             1 2 3 4 5 6 7 
             cut -d " " -f 2 
             print : 2 or 
             1,2,3,4,5,6,7,8,
             cut -d "," -f 4 
             print 4 
- passwd : change passwd 
