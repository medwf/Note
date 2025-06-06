## Working With Processes
- Use the following shortcuts to manage running processes.
  - **Ctrl+C**: Interrupt (kill) the current foreground process running in in the terminal. This sends the [SIGINT](https://www.howtogeek.com/devops/linux-signals-hacks-definition-and-more/) signal to the process, which is technically just a request most processes will honor it, but some may ignore it.
  - **Ctrl+Z**: Suspend the current foreground process running in bash. This sends the SIGTSTP signal to the process. To return the process to the foreground later, use the `fg process_name` command.
  **Ctrl+D**: Close the bash shell. This sends an `EOF` (End-of-file) marker to bash, and bash exits when it receives this marker. This is similar to running the `exit` command.
## Controlling the Screen

The following shortcuts allow you to control what appears on the screen.

  **Ctrl+L**: Clear the screen. This is similar to running the “clear” command.
  **Ctrl+S**: Stop all output to the screen. This is particularly useful when running commands with a lot of long, verbose output, but you don’t want to stop the command itself with Ctrl+C.
  **Ctrl+Q**: Resume output to the screen after stopping it with Ctrl+S.

## Moving the Cursor

   Use the following shortcuts to quickly move the cursor around the current line while typing a command.

  - **Ctrl+A** or **Home**: Go to the beginning of the line.
  - **Ctrl+E** or **End**: Go to the end of the line.
  
  - **Alt+B**: Go left (back) one word.
  - **Alt+F**: Go right (forward) one word.
  
  - **Ctrl+B**: Go left (back) one character.
  - **Ctrl+F**: Go right (forward) one character.
  - **Ctrl+XX**: Move between the beginning of the line and the current position of the cursor. This allows you to press Ctrl+XX to return to the start of the line, change something, and then press Ctrl+XX to go back to your original cursor position. To use this shortcut, hold the Ctrl key and tap the X key twice.

## Deleting Text
  Use the following shortcuts to quickly delete characters:

  - **Ctrl+D** or **Delete**: Delete the character under the cursor.
  - **Alt+D**: Delete all characters after the cursor on the current line.
  - **Ctrl+H** or **Backspace**: Delete the character before the cursor.

## Fixing Types
  These shortcuts allow you to fix typos and undo your key presses.

  - **Alt+T**: Swap the current word with the previous word.
  - **Ctrl+T**: Swap the last two characters before the cursor with each other. You can use this to quickly fix typos when you type two characters in the wrong order.
  - **Ctrl+_**: Undo your last key press. You can repeat this to undo multiple times.

## Cutting and Pasting

Bash includes some basic cut-and-paste features.

  Ctrl+W: Cut the word before the cursor, adding it to the clipboard.
  **Ctrl+K**: Cut the part of the line after the cursor, adding it to the clipboard.
  Ctrl+U: Cut the part of the line before the cursor, adding it to the clipboard.
  **Ctrl+Y**: Paste the last thing you cut from the clipboard. The y here stands for “yank”.
## Capitalizing Characters

   The bash shell can quickly convert characters to upper or lower case:
         Alt+U: Capitalize every character from the cursor to the end of the current word, converting the characters to upper case.
         Alt+L**: Uncapitalize every character from the cursor to the end of the current word, converting the characters to lower case.
        Alt+C**: Capitalize the character under the cursor. Your cursor will move to the end of the current word.

## Working With Your Command History

   You can quickly scroll through your recent commands, which are stored in your user account’s [bash history](https://www.howtogeek.com/44997/how-to-use-bash-history-to-improve-your-command-line-productivity/) file:

   **Ctrl+P** or **Up Arrow**: Go to the previous command in the command history. Press the shortcut multiple times to walk back through the history.
   **Ctrl+N** or **Down Arrow**: Go to the next command in the command history. Press the shortcut multiple times to walk forward through the history.
   **Alt+R**: Revert any changes to a command you’ve pulled from your history if you’ve edited it.

  Bash also has a special “recall” mode you can use to search for commands you’ve previously run:

  Ctrl+R**: Recall the last command matching the characters you provide. Press this shortcut and start typing to search your bash history for a command.
   Ctrl+O**: Run a command you found with Ctrl+R.
   **Ctrl+G**: Leave history searching mode without running a command.