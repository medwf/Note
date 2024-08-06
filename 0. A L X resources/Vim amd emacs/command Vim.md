Vi ( visual editor ) : that comes with unix operation system, and the unix               vi editer is a full screen editor and has two modes of operation. 

 vi filename edit filename starting at line 1_|
 _|

command mode : command witch couse action to be taken on the file      
insert mode : in witch entered text is inserted into the file 

move cursor Mode : 
        h : move left one character  
        j : move down one line 
        k : move up one line 
        l : move right one character 
        
         0 : move cursor to start of curent line 
        $ : move sursor to end of current line 
        
        w : move cursor to beginng of next word  
        b : move cursor back to beginning of preceding word 
         e : go to the end of the word 
        
        gg : fo to the first line  
        XG : go to X number of line 
        G  : go to the last line in a file 
        
insert mode : 
         
        O : open and put text in a new line above current line 
        o : open and  put text in a new line below current line 
        H : ( gg + i )
        I : insert test at the beginning of current line 
        A : insert test at the end of current line 
        i.a : insert mode 
undo : 
        xu : undo what ever you just did 
        xC-r : reundo  
        
change text : 
        r  : replace single character under curser 
        R : replace character, starting with current cursor  position (ESC)
        cw : change the current word with new text 
        cxw :  change X words beginning with character under cursor 
        
copy and past : 
        yy   : copy the current 
        Xyy yXy :   


#### Deleting Text

The following commands allow you to delete text.

x  _delete single character under cursor_|
Nx delete N characters, starting with character under cursor_|
dw _delete the single word beginning with character under cursor_|
dNw : delete N words beginning with character under cursor;  <br>  e.g., d5w deletes 5 words_|
D: delete the remainder of the line, starting with current cursor position_|
dd : delete entire current line_|
Ndd _or_ dNd :  delete N lines, beginning with the current line;  <br>  e.g., 5dd deletes 5 lines_|