# Vi ( visual editor )
- that comes with Unix operation system, and the UNIX vi editor is a full screen editor and has two modes of operation. 
- Start with: `vi filename` or `vim filename`.
- for recover file use `vi -r`.
# Modes.

## command mode.
- first mode when opened file.
- command witch Couse action to be taken on the file      
## insert mode.
- Which entered text is inserted into the file.

# Command used.
## Move cursor 
- `h` : move left one character  
- `j` : move down one line 
- `k` : move up one line 
- `l` : move right one character

- `Ctrl + f`: Scroll forward one screen.
-  `Ctrl + b`: Scroll backward one screen.
-  `Ctrl + d`: Scroll forward half a screen.
-  `Ctrl + u`: Scroll backward half a screen.
-  `Ctrl + o`: Jump to the previous location.
-  `Ctrl + i`: Jump to the next location


### In (first | last) Line. 
- `0` : move cursor to start of current line 
- `$` : move cursor to end of current line 
### By word.
- `w` : move cursor to beginning of next word  
- `b` : move cursor back to beginning of preceding word 
- `e` : go to the end of the word 
### By line
- `gg` : for to the first line  
- `XG` : go to X number of line 
- `G`  : go to the last line in a file 
- `:n`: Jump to a specific line number (replace 'n' with the line number).

## Go to Insert Mode : 
- `O` : open and put text in a new line above current line 
- `o` : open and  put text in a new line below current line 
- `H` : ( gg + i )
- `I` : insert test at the beginning of current line 
- `A` : insert test at the end of current line 
- `i` : insert mode (before the cursor).
- `a` : insert mode (after the cursor). 

## Undo : 
- `u` : undo to last text.
- `xC-r` : re undo .
- `Ctrl + r`: Redo the last undone action.

## Change Text : 
- `r`  : replace single character under curser 
- `R` : replace character, starting with current cursor  position (ESC)
- `cw` : change the current word with new text 
- `cxw` :  change X words beginning with character under cursor 
        
## Copy (Yank). 
- `yy`   : copy the current 
- `Xyy yXy` : x number of line coped with `yy`.   

## Past.
- `p` : Paste the yanked or deleted text below the cursor.

## Deleting Text
### Character.
- `x` : delete single character under cursor
- `Nx` delete N characters, starting with character under cursor
### Word.
- `dw` _delete the single word beginning with character under cursor
- `dNw` : delete N words beginning with character under cursor E.G:  `d5w` deletes 5 words.

### Line
- `D`: delete the remainder of the line, starting with current cursor position.
- `dd` : delete entire current line
- `Ndd` _or_ `dNd`:  delete N lines, beginning with the current line E.G: `5dd` deletes 5 lines.


## Searching and Replacing:
-   `/pattern`: Search forward for 'pattern'.
-   `?pattern`: Search backward for 'pattern'.
-   `n`: Move to the next search result. ->.
-   `N`: Move to the previous search result. <-.
-   `:%s/old/new/g`: Replace all occurrences of 'old' with 'new' in the entire file.
-   `:s/old/new/g`: Replace all occurrences of 'old' with 'new' in the current line.

##  Terminal command 5
 - `:!command 2`
## Secures file:
- `:X` : add password for file security 
## Saving and Quitting:
-  `:w`: Save the file.
-  `:q`: Quit Vim (if no changes were made).
-  `:q!`: Quit Vim without saving changes.
-  `:wq` or `:x`: Save and quit Vim.
-  `ZZ`: Save and quit Vim.

# config
- :set number
- :set relativenumber
- :set mouse=a
- :set tabstop=4
- :set colorscheme slat
