---
title: 2. Scripting
linkTitle: 2. Scripting
---
## Linux Shell Scripting
### Overview
This tutorial will introduce you to the basics of shell scripting using Bash. You will learn how to write, execute, and automate tasks using shell scripts.
### Prerequisites
- Basic knowledge of Linux commands (covered in the previous tutorial).
- A Linux environment to practice in.
### Objectives
By the end of this tutorial, you will:
1. Understand the basic syntax and structure of a shell script.
2. Know how to create and execute shell scripts.
3. Be able to automate tasks using shell scripts.
### 1. Introduction to Shell Scripting
#### What is a Shell Script?
A shell script is a text file containing a series of commands that the shell (command interpreter) can execute. Shell scripts can automate repetitive tasks, manage system operations, and perform complex calculations.
#### Creating a Shell Script
1. Open a terminal.
```nano myscript.sh```
1. Add the following lines to the file:
```

bash
Copy code
#!/bin/bash
# This is a comment
echo "Hello, World!"

```
1. Add the following lines to the file:
	The #!/bin/bash line is called a shebang and specifies the path to the Bash shell.
2. Save the file and exit the editor (for nano, press Ctrl+X, then Y, then Enter).
### 2. Making the Script Executable
To run the script, you need to make it executable:
```
bash
Copy code
chmod +x myscript.sh

```
### 3. Running the Script
Execute the script using the following command:
```
bash
Copy code
./myscript.sh

```
You should see the output: Hello, World!
### 4. Basic Shell Scripting Concepts
#### Variables
Variables store data that can be used and manipulated throughout the script.
```
bash
Copy code
#!/bin/bash
NAME="John"
echo "Hello, $NAME"

```
#### Comments
Comments are ignored by the shell and are used to document the script.
```
bash
Copy code
#!/bin/bash
# This is a comment
echo "Hello, World!"

```
#### Conditional Statements
Conditional statements allow you to execute commands based on certain conditions.
```
bash
Copy code
#!/bin/bash
if [ $1 -gt 10 ]; then
  echo "The argument is greater than 10"
else
  echo "The argument is 10 or less"
fi

```
#### Loops
Loops allow you to execute a series of commands multiple times.
- for loop:
```
Copy code
#!/bin/bash
for i in {1..5}; do
  echo "Welcome $i times"
done

```
- while loop:
```
Copy code
#!/bin/bash
COUNTER=0
while [ $COUNTER -lt 5 ]; do
  echo "Counter: $COUNTER"
  ((COUNTER++))
done

```
#### Functions
Functions are blocks of code that can be reused in the script.
```
bash
Copy code
#!/bin/bash
function greet() {
  echo "Hello, $1"
}
greet "John"

```
### 5. Practical Examples
#### Example 1: Backup Script
Create a script that backs up a directory to another location.
```
bash
Copy code
#!/bin/bash
SOURCE_DIR="/path/to/source"
DEST_DIR="/path/to/destination"
DATE=$(date +%Y%m%d)
tar -czf $DEST_DIR/backup_$DATE.tar.gz $SOURCE_DIR
echo "Backup completed successfully."

```
#### Example 2: User Input
Create a script that takes user input and displays a message.
```
bash
Copy code
#!/bin/bash
echo "Enter your name:"
read NAME
echo "Hello, $NAME!"

```
### Summary
In this tutorial, you learned the basics of shell scripting in Bash, including creating and executing scripts, using variables, conditional statements, loops, and functions. Shell scripting is a powerful tool for automating tasks and managing your Linux system efficiently.
### Next Steps
Proceed to the next tutorial, Linux System Administration, to learn how to manage users, processes, and packages in Linux.