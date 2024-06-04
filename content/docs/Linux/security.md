---
title: 5. Permissions and Security
linkTitle: 5. Permissions and Security
---

# Linux Permissions and Security

## Overview
This tutorial will introduce you to the basics of file permissions, ownership, and security practices in Linux. Understanding these concepts is crucial for maintaining a secure and efficient system.

## Prerequisites
- Basic knowledge of Linux commands (covered in previous tutorials).
- A Linux environment to practice in.

## Objectives
By the end of this tutorial, you will:
1. Understand Linux file permissions and ownership.
2. Know how to manage file permissions and ownership.
3. Be familiar with basic security practices, including using a firewall and securing SSH.

## 1. Understanding File Permissions and Ownership

### File Permissions
Each file and directory in Linux has three types of permissions:
- **Read (r)**: Allows reading the contents of a file or listing a directory's contents.
- **Write (w)**: Allows modifying a file or modifying a directory's contents.
- **Execute (x)**: Allows executing a file or entering a directory.

### Permission Groups
Permissions are divided into three groups:
- **Owner**: The user who owns the file.
- **Group**: Users who are part of the file's group.
- **Others**: All other users.

### Viewing Permissions
- **ls -l**:
```bash
  ls -l
```


This command lists files and directories with their permissions.
#### Understanding the Output
For example:
```
bash
Copy code
-rwxr-xr--

```
- -: File type (e.g., - for regular file, d for directory).
- rwx: Owner permissions (read, write, execute).
- r-x: Group permissions (read, execute).
- r--: Others permissions (read).
### 2. Managing File Permissions
#### Changing Permissions with chmod
- Numeric mode:
```bash
Copy code
chmod 755 filename

```
	Sets permissions to rwxr-xr-x.
- Symbolic mode:
```bash
Copy code
chmod u+rwx,g+rx,o+r filename

```
	Adds specific permissions to owner, group, and others.
#### Changing Ownership with chown
- Change owner:
```bash
Copy code
sudo chown newowner filename

```
- Change group:
```bash
Copy code
sudo chown :newgroup filename

```
- Change owner and group:
```bash
Copy code
sudo chown newowner:newgroup filename

```
#### Changing Group with chgrp
- Change group:
```bash
Copy code
sudo chgrp newgroup filename

```
### 3. Basic Security Practices
#### Using a Firewall
- UFW (Uncomplicated Firewall):
	- Install UFW:
	```bash
Copy code
sudo apt install ufw

```
	- Enable UFW:
	```bash
Copy code
sudo ufw enable

```
	- Allow specific ports (e.g., SSH):
	```bash
Copy code
sudo ufw allow 22

```
	- Check UFW status:
	```bash
Copy code
sudo ufw status

```
#### Securing SSH
- Disable root login:
	1. Open the SSH configuration file:
	```bash
Copy code
sudo nano /etc/ssh/sshd_config

```
	2. Find and change the line:
	```bash
Copy code
PermitRootLogin no

```
	3. Restart SSH service:
	```bash
Copy code
sudo systemctl restart ssh

```
- Change default SSH port:
	1. Open the SSH configuration file:
	```bash
Copy code
sudo nano /etc/ssh/sshd_config

```
	2. Change the port:
	```bash
Copy code
Port 2222

```
	3. Restart SSH service:
	```bash
Copy code
sudo systemctl restart ssh

```
	4. Allow the new port through the firewall:
	```bash
Copy code
sudo ufw allow 2222

```
### 4. Practical Examples
#### Example 1: Changing File Permissions
1. Create a file:
```bash
Copy code
touch myfile.txt

```
2. Set permissions to rwxr-xr--:
```bash
Copy code
chmod 754 myfile.txt

```
3. Verify the permissions:
```bash
Copy code
ls -l myfile.txt

```
#### Example 2: Changing Ownership and Group
1. Change the owner of myfile.txt to user:
```bash
Copy code
sudo chown user myfile.txt

```
2. Change the group of myfile.txt to group:
```bash
Copy code
sudo chgrp group myfile.txt

```
3. Verify the changes:
```bash
Copy code
ls -l myfile.txt

```
#### Example 3: Configuring UFW
1. Enable UFW:
```bash
Copy code
sudo ufw enable

```
2. Allow SSH through the firewall:
```bash
Copy code
sudo ufw allow 22

```
3. Check the status of UFW:
```bash
Copy code
sudo ufw status

```
#### Example 4: Securing SSH
1. Open the SSH configuration file:
```bash
Copy code
sudo nano /etc/ssh/sshd_config

```
2. Disable root login by changing the line to:
```bash
Copy code
PermitRootLogin no

```
3. Change the default SSH port by adding or modifying the line:
```bash
Copy code
Port 2222

```
4. Restart the SSH service:
```bash
Copy code
sudo systemctl restart ssh

```
5. Allow the new SSH port through the firewall:
```bash
Copy code
sudo ufw allow 2222

```
### Summary
In this tutorial, you learned how to manage file permissions and ownership in Linux and implemented basic security practices such as using a firewall and securing SSH. These skills are essential for maintaining a secure and efficient Linux system.
### Next Steps
Proceed to the next tutorial, Introduction to ROS, to learn the basics of the Robot Operating System (ROS), setting up a ROS workspace, and creating simple nodes.