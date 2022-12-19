
# simple_shell


![Logo](https://s3.amazonaws.com/intranet-projects-files/holbertonschool-low_level_programming/235/shell.jpeg)


## Description
Shell is a UNIX term for the interactive user interface with an operating system. The shell is the layer of programming that understands and executes the commands a user enters. In some systems, the shell is called a command interpreter.
## How it works

    -Prints a prompt and waits for a command from the user.
    -Creates a child process in which the command is checked.
    -Checks for built-ins, aliases in the PATH, and local executable programs.
    -The child process is replaced by the command, which accepts arguments.
    -When the command is done, the program returns to the parent process and prints the prompt.
    -The program is ready to receive a new command.
    -To exit: press Ctrl-D or enter "exit" (with or without a status).
    -Works also in non interactive mode.

## Installation

Install our-project 

```bash
  Installation

Clone this repository into your working directory. 
For best results,
files should be compiled with GCC and the following flags: -Wall -Wextra -Werror -pedantic -std=gnu89
```
    
## Documentation

Explains how we(@bush-da and @Teddme) build a simple shell program with limited functionality
 and what happens when you type in ls -l in your terminal and hit enter.

Prerequisites for this reading:

    -Basic understanding of the C programming language functionality including pointers, double pointers, mallocing and functional programming. Resource.
    -Basic understanding of Linux. Resource.
    -Understanding of how a file goes through the compilation process with gcc.
    -Willingness to learn new concepts.
Opening the Shell
```
Before building a simple_shell, we have to understand how it works. Before we type any commands into our shell to execute, when you open a terminal and the shell program opens up, 
it first checks for your PS1 variable in your environment variables and uses the value from PS1 to format your shell prompt. Once your shell prompt is formatted, you can then type in your command: $ ls -l .
```
PATH
```
Once all aliases and special characters have expanded, the shell looks through the first word of a command to check if it’s a built-in function before checking for a program in the PATH. 
After it checks for built-ins, the shell checks your PATH variable and uses each directory in the PATH variable to check if the command exists, in this case: isls is located in each directory?. 
(FYI, ls is a built-in, but we’ll proceed in this case as if it wasn’t).
check all of your environment variables by typing in $ env into your shell program and look for your PATH variable.

Example Output:

PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin/:bin

simple_shell program looks through each directory separated by a : to see if the ls command exists in each of these directories. When recreating the shell, 
we used a function called stat to check if the ls command existed by appending /ls to each PATH directory and entering the new PATH directory into the stat function to see if the executable file exists in each directory. 
If it didn’t exist, we recreated an error message similar to the normal output of the shell.
```
## Notice
The work is still in progress
## Usage/Examples

```
julien@ubuntu:~/shell$ ./hsh
$ ls /var
backups  cache  crash  lib  local  lock  log  mail  metrics  opt  run  snap  spool  tmp
$ echo $?
0
$ echo $$
5104
$ echo $PATH
/home/julien/bin:/home/julien/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin
$ exit 
julien@ubuntu:~/shell$ 
```


## Authors

- [@bush-da](https://www.github.com/bush-da)
- [@Teddme](https://www.github.com/Teddme)

