#### **`less` - View File Contents One Screen at a Time**

**SYNOPSIS:**  
`less [OPTIONS] [FILE]`

**Usage Examples:**

```bash
less file.txt        # View the content of `file.txt`.
less file1 file2     # View multiple files sequentially.
command | less       # View command output (e.g., `ls -l | less`).
```

**Common Key Commands Inside `less`:**

- `Space` or `PgDn`: Scroll down.
- `b` or `PgUp`: Scroll up.
- `/text`: Search for `text`.
- `n`: Jump to the next search result.
- `q`: Quit.

**Options:**

```bash
less -N            # Show line numbers.
less -S            # Disable line wrapping.
less +F            # Start in "follow" mode (like `tail -f`).
```

---

#### **`more` - View File Contents Page by Page**

**SYNOPSIS:**  
`more [OPTIONS] [FILE]`

**Usage Examples:**

```bash
more file.txt       # View `file.txt` content page by page.
command | more      # View command output (e.g., `ls -l | more`).
```

**Common Key Commands Inside `more`:**

- `Space`: Move to the next page.
- `Enter`: Move one line down.
- `q`: Quit.

**Options:**

```bash
more -d            # Display helpful prompts (e.g., `[Press space to continue]`).
more -c            # Clear the screen before displaying the next page.
```

---

#### **`head` - Display the Beginning of a File**

**SYNOPSIS:**  
`head [OPTIONS] [FILE]`

**Usage Examples:**

```bash
head file.txt       # Show the first 10 lines of `file.txt`.
head -n 20 file.txt # Show the first 20 lines.
head -c 50 file.txt # Show the first 50 bytes.
```

**Options:**

```bash
head -n N          # Display the first `N` lines.
head -c N          # Display the first `N` bytes.
```

---

#### **`tail` - Display the End of a File**

**SYNOPSIS:**  
`tail [OPTIONS] [FILE]`

**Usage Examples:**

```bash
tail file.txt       # Show the last 10 lines of `file.txt`.
tail -n 20 file.txt # Show the last 20 lines.
tail -f file.txt    # Follow file updates in real time.
```

**Options:**

```bash
tail -n N          # Display the last `N` lines.
tail -c N          # Display the last `N` bytes.
tail -f            # Follow new content added to the file.
tail -F            # Similar to `-f` but reopens the file if it is recreated.
```

---

### **Important Notes:**

1. **Use `less` for large files:** It loads the content as needed and doesn't load the entire file into memory.
2. **`more` vs `less`:** `less` is more powerful (e.g., it allows backward navigation).
3. **Combine with `head` or `tail`:** Use them together for partial file inspection:
    - Example: `head -n 50 file.txt | tail -n 10` (lines 41-50).
4. **Use `tail -f` for logs:** It's great for monitoring live log updates.