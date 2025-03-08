#### **`cd` - Change Directory**

**SYNOPSIS:**  
`cd [DIRECTORY]`

**Usage Examples:**

```bash
cd dir       # Navigate to directory `dir`.
cd           # Navigate to the home directory.
cd ~         # Also navigates to the home directory.
cd /path/to  # Navigate to an absolute path.
cd ..        # Move one level up (parent directory).
cd ../..     # Move two levels up.
cd -         # Return to the previous directory.
cd ~user     # Navigate to another user's home directory.
```

**Important Notes:**

1. Relative paths (e.g., `../folder`) are based on the current directory.
2. Absolute paths (e.g., `/home/user/folder`) start from the root.

---

#### **`pwd` - Print Working Directory**

**SYNOPSIS:**  
`pwd [OPTION]`

**Options:**

```bash
pwd           # Print the current working directory.
pwd -P        # Show the physical path, resolving symlinks.
pwd -L        # Show the logical path (default).
```

**Usage Example:**

```bash
pwd           # Displays the current directory path.
```

**Important Notes:**

- `pwd` is useful for confirming your location in the filesystem.

---

#### **`mkdir` - Create Directories**

**SYNOPSIS:**  
`mkdir [OPTION]... DIRECTORY...`

**Common Options:**

```bash
mkdir dir               # Create a single directory `dir`.
mkdir dir1 dir2         # Create multiple directories `dir1` and `dir2`.
mkdir -p path/to/dir    # Create parent directories as needed.
mkdir -v dir            # Verbose: Show directory creation details.
```

**Usage Examples:**

```bash
mkdir mydir             # Create a directory named `mydir`.
mkdir -p projects/java  # Create `projects/java`, including parent directories if they don't exist.
```

**Important Notes:**

- The `-p` option is especially useful for nested directory creation.

---

#### **`rmdir` - Remove Empty Directories**

**SYNOPSIS:**  
`rmdir [OPTION]... DIRECTORY...`

**Common Options:**

```bash
rmdir dir               # Remove an empty directory `dir`.
rmdir -p path/to/dir    # Remove `dir` and its empty parent directories.
rmdir -v dir            # Verbose: Show removal details.
```

**Usage Examples:**

```bash
rmdir mydir             # Remove the empty directory `mydir`.
rmdir -p projects/java  # Remove `projects/java` and any empty parent directories.
```

**Important Notes:**

1. `rmdir` works only for empty directories; use `rm -r` for directories with contents.
2. Use `rmdir -p` for cleaning up a hierarchy of empty directories.

---

### **Important Tips:**

1. Combine `cd` and `pwd` to verify your navigation.
2. Use `mkdir -p` to avoid errors when creating nested directories.
3. Use `rmdir` cautiously and ensure the directory is empty. For non-empty directories, use `rm -r`.