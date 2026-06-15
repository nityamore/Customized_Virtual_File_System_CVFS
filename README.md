# Customized_Virtual_File_System_CVFS
This project is a custom implementation of a Virtual File System(VFS) that simulates the core functionality of the Linux file system.

# 📁 Customized Virtual File System (CVFS)

A **Customized Virtual File System (CVFS)** developed in **C/C++** that simulates the working of an operating system's file management system. This project provides functionalities such as **file creation, reading, writing, deletion, permission handling, inode management, and command-based shell interaction**, similar to a real file system.

---

# 📌 Project Overview

The **Customized Virtual File System (CVFS)** is a command-line based project that mimics the behavior of a real operating system file system.

The system manages files using:

- **Inodes**
- **Super Block**
- **Boot Block**
- **File Table**
- **User File Descriptor Table (UFDT)**

It provides a shell interface where users can execute commands to perform file operations such as:

- Create files
- Write data into files
- Read file contents
- Delete files
- View file information
- Manage file permissions

This project helps understand **Operating System concepts**, especially **File Management Systems** and **Memory Management**.

---

# ✨ Features

✅ Create regular files  
✅ Read file contents  
✅ Write data into files  
✅ Delete files (unlink operation)  
✅ File permission management (Read/Write)  
✅ Inode-based file handling  
✅ File descriptor management  
✅ Virtual file allocation system  
✅ Command-line shell interface  
✅ Error handling mechanism  
✅ Limited file storage simulation

---

# 🛠️ Technology Used

| Technology | Purpose |
|------------|---------|
| C/C++ | Core programming language |
| Data Structures | Linked List for Inode Management |
| Memory Allocation | Dynamic Memory (`malloc`, `free`) |
| Operating System Concepts | File System Simulation |
| Linux System Calls | Command execution |

---

# 📂 Project Structure

```text
Customized-Virtual-File-System/
│── program555.cpp      # Main source code
│── README.md           # Project documentation
```

---

# ⚙️ Core Components

## 1. Boot Block

The **Boot Block** stores information required during the initialization of the virtual file system.

```cpp
struct BootBlock
{
    char Information[100];
};
```

---

## 2. Super Block

The **Super Block** keeps track of:

- Total available inodes
- Free inodes

```cpp
struct SuperBlock
{
    int TotalInodes;
    int FreeInodes;
};
```

---

## 3. Inode

An **inode** stores metadata about a file.

It contains:

- File name
- File size
- File type
- Permissions
- Buffer
- Reference count

```cpp
struct Inode
{
    char FileName[20];
    int InodeNumber;
    int FileSize;
    int ActualFileSize;
    int FileType;
    int ReferenceCount;
    int Permission;
    char *Buffer;
};
```

---

## 4. File Table

Stores information about currently opened files.

Includes:

- Read Offset
- Write Offset
- File Mode
- Inode Pointer

---

## 5. UAREA (User Area)

Maintains the **User File Descriptor Table (UFDT)**.

Used to manage opened files.

---

# 💻 Supported Commands

| Command | Description |
|---------|-------------|
| `help` | Display all available commands |
| `man <command>` | Show manual page of command |
| `creat <filename> <permission>` | Create new file |
| `write <fd>` | Write data to file |
| `read <fd> <size>` | Read data from file |
| `ls` | Display all files |
| `unlink <filename>` | Delete a file |
| `clear` | Clear terminal screen |
| `exit` | Exit CVFS |

---

# 🔐 File Permissions

The project supports **basic file permissions**.

| Permission | Value | Meaning |
|------------|------|----------|
| Read | `1` | Read only |
| Write | `2` | Write only |
| Read + Write | `3` | Read and write |

### Example

```bash
creat demo.txt 3
```

This creates a file with **read and write permission**.

---

# ▶️ How to Run Project

## Step 1: Clone Repository

```bash
git clone <your-github-repository-link>
```

---

## Step 2: Navigate to Project Folder

```bash
cd Customized-Virtual-File-System
```

---

## Step 3: Compile the Program

Using **g++ compiler**:

```bash
g++ program555.cpp -o cvfs
```

---

## Step 4: Run the Program

### Linux / Mac

```bash
./cvfs
```

### Windows

```bash
cvfs.exe
```

---

# 🧪 Sample Commands

### Create a File

```bash
creat notes.txt 3
```

Output:

```text
File gets successfully created with FD 3
```

---

### Write into File

```bash
write 3
```

Enter data:

```text
Hello Welcome to CVFS
```

Output:

```text
24 bytes gets successfully written
```

---

### Read File Content

```bash
read 3 10
```

Output:

```text
Read operation is successful
Data from file is : Hello Wel
```

---

### List Files

```bash
ls
```

Output:

```text
-----------------------------------------------
------ Marvellous CVFS Files Information ------
-----------------------------------------------
1       notes.txt      24
-----------------------------------------------
```

---

### Delete File

```bash
unlink notes.txt
```

Output:

```text
File gets successfully deleted
```

---

### Exit Program

```bash
exit
```

Output:

```text
Thank you for using Marvellous CVFS
Deallocating all the allocated resources
```

---

# 📸 Sample Output

```text
Booting process of Marvellous CVFS is done

Marvellous CVFS : Super block gets initialised successfully
Marvellous CVFS : DILB created successfully
Marvellous CVFS : UAREA gets initialised successfully

-----------------------------------------------
----- Marvellous CVFS started successfully ----
-----------------------------------------------

Marvellous CVFS : >
```

---

# 🧠 Concepts Used

This project is based on important **Operating System and Data Structure concepts**:

### Operating System Concepts
- Virtual File System
- File Management
- Inode Structure
- File Descriptor
- Memory Allocation
- File Permissions

### Data Structure Concepts
- Linked List
- Dynamic Memory Allocation
- Pointer Management

### Programming Concepts
- Structures
- Functions
- Macros
- Error Handling
- Command Parsing
- Dynamic Memory

---

# 🎯 Learning Outcome

By developing this project, one can learn:

- How operating systems manage files internally
- Working of inode-based file systems
- File descriptors and memory allocation
- Shell command implementation
- Dynamic memory management
- Permission handling
- Low-level system design concepts

---

# 🚀 Future Enhancements

Some improvements that can be added in the future:

- 🔹 File Encryption & Decryption  
- 🔹 Password Protected Files  
- 🔹 Directory Support  
- 🔹 File Rename Feature  
- 🔹 Copy/Paste File Functionality  
- 🔹 Search File Feature  
- 🔹 GUI Interface  
- 🔹 Multi-user Access Support  
- 🔹 File Compression

---

# 👨‍💻 Author

**Nitya Rajesh More**  

Third Year Information Technology Student

---

# ⭐ GitHub Tip

If you found this project useful, don't forget to **Star ⭐ the repository**.
