---
title: Basic Commands
linkTitle: Basic
---
## Introduction to Linux
### Overview
This tutorial will introduce you to the basics of the Linux operating system, including fundamental commands and file system navigation.
### Prerequisites
- A computer with a Linux distribution installed (e.g., Ubuntu, Fedora).
- Basic understanding of using a computer.
### Objectives
By the end of this tutorial, you will:
1. Understand the basic structure of the Linux file system.
2. Know how to use basic Linux commands to navigate and manage files and directories.
3. Be able to perform basic file operations from the command line.
### 1. Understanding the Linux Directory Structure
Linux has a hierarchical file system. Some of the common directories are:
- /: Root directory
- /home: Contains user home directories
- /bin: Essential binary executables
- /etc: Configuration files
- /var: Variable files like logs
- /usr: User programs and utilities
### 2. Basic Linux Commands
#### Navigating the File System
- pwd
Outputs the current directory you are in.
- ls: List directory contents
```bash
Copy code
ls
```
Shows the files and directories in the current directory.
- cd: Change Directory
```bash
Copy code
cd /path/to/directory
```
Changes the current directory to the specified path.
#### Managing Files and Directories
- mkdir: Make Directory
```bash
Copy code
mkdir new_directory
```
Creates a new directory named new_directory.
- rmdir: Remove Directory
```bash
Copy code
rmdir directory_name
```
Removes an empty directory named directory_name.
- touch: Create a new file
```bash
Copy code
touch new_file.txt
```
Creates an empty file named new_file.txt.
- rm: Remove File
```bash
Copy code
rm file_name.txt
```
Deletes the file named file_name.txt.
- cp: Copy Files
```bash
Copy code
cp source_file.txt destination_file.txt
```
Copies source_file.txt to destination_file.txt.
- mv: Move/Rename Files
```bash
Copy code
mv old_name.txt new_name.txt
```
Renames or moves old_name.txt to new_name.txt.
#### Viewing and Editing Files
- cat: Concatenate and display file contents
```bash
Copy code
cat file_name.txt
```
Displays the content of file_name.txt.
- nano or vim: Text editors
```bash
Copy code
nano file_name.txt
```
Opens file_name.txt in the nano text editor.
### 3. Practical Examples
#### Example 1: Creating and Navigating Directories
1. Open your terminal.
2. Create a new directory named test_directory:
```bash
Copy code
mkdir test_directory
```
1. Navigate into test_directory:
```bash
Copy code
cd test_directory
```
1. Verify your current directory:
```bash
Copy code
pwd
```
#### Example 2: Creating, Viewing, and Deleting a File
1. Create a new file named test_file.txt:
```bash
Copy code
touch test_file.txt
```
1. List the directory contents to verify the file creation:
```bash
Copy code
ls
```
1. Display the contents of test_file.txt (it should be empty):
```bash
Copy code
cat test_file.txt
```
1. Remove the file:
```bash
Copy code
rm test_file.txt
```
1. List the directory contents again to verify the deletion:
```bash
Copy code
ls
```
### Summary
In this tutorial, you learned the basics of navigating the Linux file system and performing simple file and directory operations. These skills are fundamental for working efficiently in a Linux environment.
### Next Steps
Proceed to the next tutorial, Linux Shell Scripting, to learn how to automate tasks using shell scripts.
```kotlin
Copy code
```