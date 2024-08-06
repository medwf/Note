1.  Opening a File:
    
    - vim filename`: Opens the specified file in Vim.
    - vim`: Opens Vim without a specific file.
    - vi -r filename  recover filename that was being edited when system crashed
1.  Navigation:
    
    -   `h`: Move the cursor left.
    -   `j`: Move the cursor down.
    -   `k`: Move the cursor up.
    -   `l`: Move the cursor right.
    -   `G`: Move to the end of the file.
    -   xG: jumb to x line  
    -   `gg`: Move to the beginning of the file.
    -   `Ctrl + f`: Scroll forward one screen.
    -   `Ctrl + b`: Scroll backward one screen.
    -   `Ctrl + d`: Scroll forward half a screen.
    -   `Ctrl + u`: Scroll backward half a screen.
    -   `Ctrl + o`: Jump to the previous location.
    -   `Ctrl + i`: Jump to the next location.
    -   `:n`: Jump to a specific line number (replace 'n' with the line number).
3.  Editing Text:
    
    -   `i`: Enter insert mode (insert before the cursor).
    -   `a`: Enter insert mode (insert after the cursor).
    -   `o`: Insert a new line below the current line and enter insert mode.
    -   `O`: Insert a new line above the current line and enter insert mode.
    -   `x`: Delete the character under the cursor.
    -   `dd`: Delete the current line.
    -  `dw` : Delete the next word .
    -   `yy`: Yank (copy) the current line.
    -   `p`: Paste the yanked or deleted text below the cursor.
    -   `u`: Undo the last action.
    -   `Ctrl + r`: Redo the last undone action.
4.  Saving and Quitting:
    
    -   `:w`: Save the file.
    -   `:q`: Quit Vim (if no changes were made).
    -   `:q!`: Quit Vim without saving changes.
    -   `:wq` or `:x`: Save and quit Vim.
    -   `ZZ`: Save and quit Vim.
5.  Searching and Replacing:
    
    -   `/pattern`: Search forward for 'pattern'.
    -   `?pattern`: Search backward for 'pattern'.
    -   `n`: Move to the next search result.
    -   `N`: Move to the previous search result.
    -   `:%s/old/new/g`: Replace all occurrences of 'old' with 'new' in the entire file.
    -   `:s/old/new/g`: Replace all occurrences of 'old' with 'new' in the current line.
 6. Securise file:
       `:X` : add password for file security 
 7 . terminal command 5
 :!command 2
 8 set
        :set number
        :set relativenumber
        :set mouse=a
        :set tabstop=4
        :set colorscheme slat