![[permission.png]]

In Linux, file permissions are a fundamental aspect of the operating system's security model. They determine who can read, write, or execute a file. Here's a breakdown of how permissions work:

### Permission Types
Each file and directory has three types of permissions:
1. **Read (r)**: Allows viewing the contents of a file or listing the contents of a directory.
2. **Write (w)**: Allows modifying the contents of a file or adding/removing files in a directory.
3. **Execute (x)**: Allows running a file as a program or entering a directory.

### Permission Categories
Permissions are assigned to three categories of users:
1. **Owner**: The user who owns the file.
2. **Group**: A group of users who share the same permissions.
3. **Others**: All other users.
	=> change user or group should use `chown`.
### Permission Representation
Permissions are represented using a combination of letters and symbols. For example, `-rwxr-xr--` represents:
- `-`: Indicates a regular file (a `d` would indicate a directory).
- `rwx`: Owner has read, write, and execute permissions.
- `r-x`: Group has read and execute permissions.
- `r--`: Others have read-only permissions.
    => change using `chmod`.
### Example
Here's an example of how permissions might look for a file:
```bash
-rw-r--r-- 1 user group 1234 Dec 23 17:14 example.txt
```
- `-rw-r--r--`: Permissions (read and write for owner, read-only for group and others).
- `1`: Number of hard links.
- `user`: Owner of the file.
- `group`: Group associated with the file.
- `1234`: File size in bytes.
- `Dec 23 17:14`: Last modification date and time.
- `example.txt`: File name.
