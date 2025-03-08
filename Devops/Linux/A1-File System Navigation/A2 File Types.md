In Linux, files are categorized into several types, each serving a different purpose. Here are the main types of files you'll encounter:

### 1. Regular Files
These are the most common type of files and can contain text, data, or program instructions. Examples include documents, images, and executable files.
	=> created by `touch` or text editor

### 2. Directory Files
Directories are special files that contain information about other files and directories. They help organize the file system in a hierarchical structure.
1. `.`  : working Directory 
2. `..` : parent Directory
3. `~` : user directory.
4. `/` : root directory.

### 3. Link Files
Links are pointers to other files. There are two types of links:
- **Hard Links**: Direct pointers to the data of another file.
- **Symbolic (Soft) Links**: Pointers to another file's name.
	=> created by `cp` and `ln` 

### 4. Character Special Files
These files represent devices (`/dev`) that handle data as a stream of characters, such as keyboards and serial ports.

### 5. Block Special Files
These files represent devices that handle data in blocks, such as hard drives and disk drives.

### 6. Socket Files
Sockets are used for inter-process communication, allowing processes to communicate over the network.

### 7. Named Pipe Files
Named pipes, also known as FIFOs (First In, First Out), allow processes to communicate with each other by reading and writing data in a specific order.
