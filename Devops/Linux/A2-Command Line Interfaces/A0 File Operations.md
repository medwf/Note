#### **`ls` - List Directory Contents**

**SYNOPSIS:**  
- `ls [OPTION]... [FILE]...`

**Common Options:**
```bash
ls -a    # List all files, including hidden ones (., ..).
ls -A    # List hidden files but exclude . and ..

ls -l    # Long format (permissions, owner, size, etc.).
ls -o    # Exclude group information in long format.
ls -h    # Show sizes in human-readable format (k, M, G).

ls -p    # Append a slash (/) to directories.
ls -1    # Display one file per line.
ls -n    # Show numeric user and group IDs.
ls -m    # Separate file names with commas.

ls -t    # Sort by modification time, newest first.
ls -r    # Reverse the sorting order.
ls -i    # Display the inode number for each file.
ls -s    # Show the allocated size of each file.
ls -v    # Sort in a natural order (e.g., 1, 2, 10).

ls -d    # Show directories themselves, not their contents.
ls --time-style=long-iso  # Use ISO format for date and time.
```

---

#### **`cp` - Copy Files or Directories**

**SYNOPSIS:**

- `cp [OPTION]... [-T] SOURCE DEST`
- `cp [OPTION]... SOURCE... DIRECTORY`
- `cp [OPTION]... -t DIRECTORY SOURCE...`

**Common Options:**

```bash
cp -r    # Copy directories recursively.
cp -s    # Create a symbolic link instead of copying.
cp -l    # Create a hard link instead of copying.

cp -i    # Prompt before overwriting files.
cp -v    # Show details of the operation (verbose).
```

**Usage Example:**

```bash
cp file1 file2    # Copy file1 to file2.
cp -r dir1 dir2   # Recursively copy dir1 to dir2.
```

---

#### **`mv` - Move or Rename Files**

**SYNOPSIS:**  
- `mv [OPTION]... SOURCE... DIRECTORY`

**Common Options:**

```bash
mv -i    # Prompt before overwriting files.
mv -n    # Do not overwrite any existing files.
mv -f    # Force overwrite without prompting.
mv -v    # Show details of the operation (verbose).
```

**Usage Example:**

```bash
mv file1 file2    # Rename file1 to file2.
mv file1 dir/     # Move file1 to directory dir/.
```

---

#### **`rm` - Remove Files or Directories**

**SYNOPSIS:**  
`rm [OPTION]... [FILE]...`

**Common Options:**

```bash
rm -r    # Remove directories and their contents recursively.
rm -d    # Remove an empty directory.
rm -i    # Prompt before every removal.
rm -I    # Prompt once before removing more than three files.
rm -f    # Ignore non-existent files, no prompt.
rm -v    # Show details of the removal (verbose).

# Removing files with a leading dash (-):
rm -- -file
rm ./-file
```

**Usage Example:**

```bash
rm file1           # Remove file1.
rm -r dir          # Remove directory dir and its contents.
```

---

#### **`touch` - Create or Update Files**

**SYNOPSIS:**  
`touch [OPTION]... FILE...`

**Common Options:**

```bash
touch -c    # Do not create any files if they do not exist.
touch -m    # Update only the modification time.
touch -t    # Set a custom timestamp: [[CC]YY]MMDDhhmm[.ss]
```

**Usage Example:**

```bash
touch file1        # Create file1 or update its timestamp.
touch -t 202412101230.45 file1  # Set timestamp to Dec 10, 2024, 12:30:45.
```

---

#### **`cat` - Concatenate and Display File Contents**

**SYNOPSIS:**  
- `cat [OPTION]... [FILE]...`

**Common Options:**

```bash
cat -        # Read input from the keyboard.

-A           # Show all, equivalent to -vET.
-b           # Number non-empty lines (overrides -n).
-n           # Number all lines.
-E           # Show `$` at the end of each line.
-T           # Show tabs as `^I`.
-v           # Display non-printing characters.

-s           # Squeeze multiple blank lines into one.
-e           #  equivalent to -vE
```

**Usage Example:**

```bash
cat file1           # Display the content of file1.
cat -               # Type input from keyboard, Ctrl+D to exit.
cat file1 file2 > merged.txt  # Concatenate file1 and file2 into merged.txt.
```

---

### **Important Notes:**

1. Use `man [command]` for detailed information about any command.
2. Combine options to achieve more functionality, e.g., `ls -lh` for a detailed, human-readable list.
3. Always use `-i` or `-I` with `rm`, `cp`, or `mv` to avoid accidental data loss.