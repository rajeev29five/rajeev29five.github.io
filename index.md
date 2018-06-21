---
layout: default
---
---

## What is a Terminal?

A terminal is text-based application used for viewing, manipulating and handling files on your computer. It can be considered as Windows' File Explorer or Mac's Finder without a graphical interface. It is also known as **CLI, command line, console, prompts**. 

This is what a prompt looks like on linux system.

<p class="terminal">Terminal</p>
```
username@localhost~$


```

<br>
A prompt has four parts.

`username `:  Shows the username of current user. 

`hostname `:  This is the name of your computer.

`absolutepathname `: Shows the absolute path name of current working directory. In this case it is **home** directory represented by the symbol tilde(~).

`currentuser `: The shell prompt normally ends in a **$** sign which means that the user is logged in as normal user with restricted access to resources, while **#** indicates that you are logged in as **root** also know as **super user** and can access nearly all resources which is other wise accessible to few programs. 

**NOTE :** You should avoid logging in as root unless necessary as it makes your system vulnerable.

## What is a command?
A command is an instruction given to computer to do something, such as run a program or group of programs. These commands are given to computer by typing it in command-line or a terminal and then pressing ENTER key, which in turn will pass them to the shell. Most of the commands take the following form.

> command [OPTIONS] additional_arguments

`command name `: The command you want to give to the computer.

`[OPTIONS] `: 

`additional_arguments `: additional information such as file or directory name. Sometimes it is optional 

## 1. ls

**ls** stands for list. It lists the contents of directory(file(s) and subdirectory(ies)) with additional information. 

**ls** takes the following form.

> ls [OPTIONS] arguments

Type the command

<p class="terminal">Terminal</p> 
```
username@localhost~$ ls
Desktop	Downloads	Pictures	Templates
Documents	Music		Public		Videos
username@localhost~$ 

```

Some of the most common arguments(also known as flags) that can be used with **ls** are :

`-a or --all` : lists the contents of directroy including hidden file(s) or directory(ies).
`-l` : lists the contents using long listing formats.

**NOTE :** In linux hidden file(s) or directory(ies) can be easily distinguished from regular because their name are prefixed by a period(i.e **dot character '.'** ).

Type the ls command with `-a or --all` argument in **Terminal**.

<p class="terminal">Terminal</p> 
```
username@localhost~$ ls -a
.		  .cache	Music		Videos
..		  Desktop	Pictures
.bash_history   Documents	Public
.bashrc	  Downloads	Templates
username@localhost~$ 

```

**`.`** represents the current working directory **`..`** and all the other file(s) or directory(ies) prefixed by a period(dot) such as **.bashrc**, **.cache**, etc are hidden.

Next type the ls command with `-l` argument in your **Terminal**.
<p class="terminal">Terminal</p> 
```
username@localhost~$ ls -l
drwxr-xr-x 2 username username 4096 Apr  8 16:45 Desktop
drwxr-xr-x 2 username username 4096 Jun 10 00:08 Documents
drwxr-xr-x 2 username username 4096 Jun 21 09:18 Downloads
drwxr-xr-x 2 username username 4096 Jun 11 05:47 Music
drwxr-xr-x 2 username username 4096 Jun 13 04:56 Pictures
drwxr-xr-x 2 username username 4096 Jul 24  2017 Public
drwxr-xr-x 2 username username 4096 Jul 24  2017 Templates
drwxr-xr-x 2 username username 4096 Jun 17 22:21 Videos
username@localhost~$ 

```
<p></p>
1. First column shows the file's type and file mode bits. Type is shown as `-` for regular files, in above case type is `d` which means it is a directory. The file mode bits are read, write(to change), and execute(to run it as a program) for the file's owner, its group, and other users, respectively; a dash means the permission is not granted.
2. The number of hard links to the file. 
3. The user who owns the file. 
4. The file's group. 
5. The file's size in bytes. 
6. The date the file was last modified. 

To learn more about **ls** or any command, type 
> **man command_name** 

in your **Terminal**. The **man** command will output manual for the particular command to the standard output. 

## 2. mkdir

**mkdir** stands for make directory. A directory is a folder. Command creates directory(ies), if they do not already exist.

**mkdir** takes the following form.

> mkdir [OPTIONS] name_of_directory

<p class="terminal">Terminal</p>
```
username@localhost~$ mkdir basiccommands
username@localhost~$ 



```

<br>

## 3. touch

An empty file that does not exist is created.

**touch** takes the following form.

> touch [OPTIONS] name_of_file

Type the following command in your teminal and the press ENTER.

<p class="terminal">Terminal</p>
```
username@localhost~$ touch newfile.txt
username@localhost~$



```

Nothing happened? :(

Well something did happen a file named **newfile.txt** has been created in the current working directory. To check whether the file has been created or not, list the contents of your current working directory. You know the command for that, don't you?
<br>

## 4. cd

**cd** stands for change directory. Used to traverse directory(ies). If name of directory is not supplied, working directory is changed to root or home. If **`..`** is supplied, working directory is set to immediate previous of current working directory. If **`-`** is supplied old working directory is set to current working directory, if the directory change is successful, the absolute pathname of the new working directory is written to the standard  output.

<p class="terminal">Terminal</p>
```
username@localhost~$




```
<br>

## 5. pwd

**pwd** prints absolute pathname of the current working directory. 

<p class="terminal">Terminal</p>
```
username@localhost~$ pwd
/home/username
username@localhost~$


```
<br>

## 6. chmod


<p class="terminal">Terminal</p>
```
username@localhost~$




```
<br>

## 7. head

Prints the first 10 lines of each file to standard output. In case more than one file is specified, standard output of each file is preceded by header giving the file name. If **`-n`** or **`--lines`** is supplied, then **`n`** number of lines are printed to standard output. Let us see the content of the file that we created using touch command.

<p class="terminal">Terminal</p>
```
username@localhost~$ head newfile.txt
I'm first line.
I'm second line.
I'm third line.
.
.
.
I'm last line.
username@localhost~$ 
```


<br>

## 8. tail

**tail** prints the last 10 lines of each file to standard output. In case more than one file is specified, standard output of each file is preceded by header giving the file name. If **`-n`** or **`--lines`** is supplied, then **n** number of lines are printed to standard output.

<p class="terminal">Terminal</p>
```
username@localhost~$ tail newfile.txt




```
<br>
