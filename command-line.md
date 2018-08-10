---
layout: default
---
---

## What is a command?
A command is an instruction given to computer to do something, such as run a program or group of programs. These commands are given to computer by typing it in command-line or a terminal and then pressing ENTER key, which in turn will pass them to the shell. Most of the commands take the following form.

> command [OPTIONS] arguments

`command name `: The command you want to give to the computer.

`[OPTIONS] `: Known as flags or arguments to specify command how to act. These are often preceded by single(`-`) or double(`--`) dash and can be left out in case of certain commands.

`arguments `: additional information that tells the command to what to work on such as file or directory name. It may or may not be necessary depending on the command used.

## What is a Terminal?

A terminal is text-based application used for viewing, manipulating and handling files on your computer. It can be considered as Windows' File Explorer or Mac's Finder without a graphical interface. It is also known as **CLI, command line, console, prompts**. 

This is what a prompt looks like on linux system.

<p class="terminal">Terminal</p>
```
username@localhost:~$


```

<br>
A prompt has four parts.

`username `:  Shows the username of current user. 

`hostname `:  This is the name of your computer.

`absolutepathname `: Shows the absolute path name of current working directory. In this case it is **home** directory represented by the symbol tilde(~).

`currentuser `: The shell prompt normally ends in a **$** sign which means that the user is logged in as normal user with restricted access to resources, while **#** indicates that you are logged in as **root** also know as **super user** and can access nearly all resources which is other wise accessible to few programs. 

**NOTE :** You should avoid logging in as root unless necessary as it makes your system vulnerable.

<br>

## 1. ls

**ls** stands for list. It lists the contents of directory(file(s) and subdirectory(ies)) with additional information. 

**ls** takes the following form.

> ls [OPTIONS] arguments

Type the command

<p class="terminal">Terminal</p> 
```
username@localhost:~$ ls
Desktop  Documents  Downloads  Music  Pictures  Public  Templates  Videos
username@localhost:~$ 

```

Some of the most common arguments(also known as flags) that can be used with **ls** are :

`-a or --all` : lists the contents of directroy including hidden file(s) or directory(ies).
`-l` : lists the contents using long listing formats.

**NOTE :** In linux hidden file(s) or directory(ies) can be easily distinguished from regular because their name are prefixed by a period(i.e **dot character '.'** ).

Type the ls command with `-a or --all` argument in **Terminal**.

<p class="terminal">Terminal</p> 
```
username@localhost:~$ ls -a
.               .cache          Music           Videos
..              Desktop         Pictures
.bash_history   Documents       Public
.bashrc         Downloads       Templates
username@localhost:~$ 

```

**`.`** represents the current working directory **`..`** and all the other file(s) or directory(ies) prefixed by a period(dot) such as **.bashrc**, **.cache**, etc are hidden.

Next type the ls command with `-l` argument in your **Terminal**.
<p class="terminal">Terminal</p> 
```
username@localhost:~$ ls -l
drwxr-xr-x 2 username username 4096 Apr  8 16:45 Desktop
drwxr-xr-x 2 username username 4096 Jun 10 00:08 Documents
drwxr-xr-x 2 username username 4096 Jun 21 09:18 Downloads
drwxr-xr-x 2 username username 4096 Jun 11 05:47 Music
drwxr-xr-x 2 username username 4096 Jun 13 04:56 Pictures
drwxr-xr-x 2 username username 4096 Jul 24  2017 Public
drwxr-xr-x 2 username username 4096 Jul 24  2017 Templates
drwxr-xr-x 2 username username 4096 Jun 17 22:21 Videos
username@localhost:~$ 

```
<p></p>
1. First column shows the file's type and file mode bits. Type is shown as `-` for regular files, in above case type is `d` which means it is a directory. We'll discuss about file mode bits later while learning about **chmod** command.
2. The number of hard links to the file. 
3. The user who owns the file. 
4. The file's group. 
5. The file's size in bytes. 
6. The date the file was last modified.

Using name of directory as an argument to **ls** command will list the contents of directory.

<p class="terminal">Terminal</p> 
```
username@localhost:~$ ls Downloads/
bootstrap-4.0.0-dist 	
bootstrap-4.0.0-dist.zip
opencv-python-tutroals
Westworld The Passenger
username@localhost:~$ 

```

A simple trick, instead of typing the whole thing in **Terminal** yourself press **tab key** after typing some part of the command.

For instance after typing 

> username@localhost:~$ **ls Dow** 

hit **tab** key once to autocomplete your command.

To list the contents of directory that is located deep within a directory, provide absolute pathname of the directory whose content you want to as an argument to **ls** command.

The below example lists the contents of **ChildFolder** that is 3 levels deep inside the **GreatParentFolder**.

**Remiders** do not type the whole name yourself hit **tab** as much as you can. 

<p class="terminal">Terminal</p> 
```
username@localhost:~$ ls GreatGrandParentFolder/GrandParentFolder/ParentFolder/ChildFolder/         
child.txt
username@localhost:~$ 

```

To learn more about **ls** or any command, type

> **man command_name** 

in your **Terminal**. The **man** command will output manual for the particular command to the standard output. 

**Exercise :** Explore different arguments or flags with the help of **man** command that you can use with **ls** command.

<br>

## 2. mkdir

**mkdir** stands for make directory. A directory is a folder. Command creates directory(ies), if they do not already exist.

**mkdir** takes the following form.

> mkdir [OPTIONS] name_of_directory

Let's create a directory on which we can experiment.

Type in the following command in your **Terminal**. Use whatever name you want for your directory, I'm naming my directory basiccommands.


<p class="terminal">Terminal</p>
```
username@localhost:~$ mkdir basiccommands
username@localhost:~$ 



```

**NOTE :** Be careful while using space(s) in naming you directory. Simply using space(s) in name will create multiple directories. To have spaces in name use backslash `\` before space and just after the word  `$ mkdir my\ directory`.

You can use **ls** command to check if your directory has been created or not.

To create directory within another directory, provide the absolute path as an argument to **mkdir**. Let's create another directory within **basiccommands** directory name **GreatGrandParentFolder**. 

<p class="terminal">Terminal</p>
```
username@localhost:~$ mkdir basiccommands/GreatGrandParentFolder
username@localhost:~$ 



```

Similarly create directory within **GreatGrandParentFolder** named **GrandParentFolder**... till **GreatGrandChildFolder**. We will use this deep directory structure with our next command that is **cd**.

<br>

## 3. cd

**cd** stands for change directory. Used to traverse directory(ies). 

Command takes the following form, 

> cd [OPTIONS] [dir]

If name of directory(in above case "dir") is not supplied, working directory is changed to root or home. If **`..`** is supplied, working directory is set to the directory immediate previous of current working directory. If **`-`** is supplied old working directory is set to current working directory, if the directory change is successful, the absolute pathname of the new working directory is written to the standard  output.

For now let's change our working directory to the directory you created with the help of **mkdir** command.

<p class="terminal">Terminal</p>
```
username@localhost:~$ cd basiccommands
username@localhost:~/basiccommands$



```
<br>

As mentioned before **`..`** with **cd** changes the working directory to immediate previous of the current working directory.

<p class="terminal">Terminal</p>
```
username@localhost:~/basiccommands$ cd ..
username@localhost:~$



```

In above example current directory is **basiccommands** and its immediate previous is the **root or home** directory(denoted by **`~`**). 

<br>

## 4. pwd

**pwd** stands for "print working directory", it prints absolute pathname of the current working directory. 

<p class="terminal">Terminal</p>
```
username@localhost:~/basiccommands$ pwd
/home/username/basiccommands
username@localhost:~/basiccommands$


```
<br>

## 5. touch

An empty file that does not already exists in the current working directory is created.

**touch** takes the following form.

> touch [OPTIONS] name_of_file

Type the following command in your teminal and the press ENTER.

<p class="terminal">Terminal</p>
```
username@localhost:~/basiccommands$ touch newfile.txt
username@localhost:~/basiccommands$



```

Nothing happened? :(

Well something did happen a file named **newfile.txt** has been created in the current working directory. To check whether the file has been created or not, list the contents of your current working directory. You know the command for that, don't you?

<br>

## 6. chmod

**chmod** stands for change mode. Changes the file or directory(ies) mode bits(access permissions) of each given file according to _mode_, which can either be an octal number(digits 0 through 7) representing the bit pattern for new mode bits or a symbolic representations.

Before learning more about **mode bits**. Let us see the current access permission of our file. For that use `ls -l` command.

<p class="terminal">Terminal</p>
```
username@localhost:~/basiccommands$ ls -l
-rw-rw-r-- 1 username username 51 Jun 24 20:00 newfile.txt
username@localhost:~/basiccommands$



```

The file mode bits are **read** denoted by **r** indicating that user has just reading privileges, **write** denoted by **w** indicating user can make changes, and **execute** denoted by **x** indicating that user can run it as a program, for the file's owner, its group, and other users, respectively; a dash means the permission is not granted. 

Let's change the mode bit using symbolic notation. Symbolic notation takes the following form

> chmod [reference][operator][modes] filename

`reference : ` There are four references **u(user/owner), g(group), o(other)** and **a(all u, g and o)**.

`operator : ` There are three operators **+(add mode bit to specified reference), -(remove mode bit from specified reference)** and **=(modes specified should be made exact modes for specified reference)**. 

`mode : ` There six modes **r(read), w(write), x(execute), X(special execute), s(setuid/gid)** and **t(sticky)**.

Type the command in your **Terminal** as shown below.

<p class="terminal">Terminal</p>
```
username@localhost:~/basiccommands$ chmod u=rwx,g=rw,o=r newfile.txt
username@localhost:~/basiccommands$



```

`ls -l` again to see the difference between old and new access permissions.

Now using the octal permissions. The current access permission of **newfile.txt** is **rwx** for **user/owner**, **rw** for **group** and **r** for **other**. Let's change the permission for **user** from **r** to **rx** using octal notation and leave **user/owner** and **group** as it is.

<p class="terminal">Terminal</p>
```
username@localhost:~/basiccommands$ chmod 765 newfile.txt
username@localhost:~/basiccommands$



```

Type `ls -l` and you will notice that now the permission for **newfile.txt** looks something like this `-rwxrw-r-x`.

The octal notation **7, 6 and 5** individually represent **user/owner**, **group** and **other** respectively. In fact these numbers are combination of digit `4` that represents **read**, `2` that represents **write**, `1` that represents **execute** and `0` that represents **no permission**. Therefore in case of above example

**7** = **4(read)** + **2(write)** + **1(execute)**

**6** = **4(read)** + **2(write)** + **0(no permission)**

**5** = **4(read)** + **0(no permission)** + **1(execute)**

To change mode bits of a directory use `-R` argument with chmod as shown below. Using `-R` with **chmod** will recursively change the mode bits of all the files inside that directory to specified modes.

<p class="terminal">Terminal</p>
```
username@localhost:~/basiccommands$ chmod 777 -R directory
username@localhost:~/basiccommands$



```
<br>

Try different octal notation to change file access permissions.

<br>

## 7. head

Prints the first 10 lines of each file to standard output. In case more than one file is specified, standard output of each file is preceded by header giving the file name. If **`-n`** or **`--lines`** is supplied **`n`** number of lines are printed to standard output. Let us see the content of the file that we created using touch command.

> head [OPTIONS] FILE(s)

<p class="terminal">Terminal</p>
```
username@localhost:~/basiccommands$ head newfile.txt
I'm first line.
I'm second line.
I'm third line.
.
.
.
I'm tenth line.
username@localhost:~/basiccommands$ 

```
<br>
To print first **n** number of line(s) of a file. In the following example I'm printing first **3** lines of **newfile.txt**. 

<p class="terminal">Terminal</p>
```
username@localhost:~/basiccommands$ head -n 3 newfile.txt
I'm first line.
I'm second line.
I'm third line.
username@localhost:~/basiccommands$




```
<br>
**NOTE :** As an exercise use `-n or --lines` with multiple files.
<br>

## 8. tail

**tail** prints the last 10 lines of each file to standard output. In case more than one file is specified, standard output of each file is preceded by header giving the file name. If **`-n`** or **`--lines`** is supplied, then **n** number of lines are printed to standard output.

> tail [OPTIONS] FILE(s)

<p class="terminal">Terminal</p>
```
username@localhost:~/basiccommands$ tail newfile.txt
I'm eleventh line.
I'm twelveth line.
.
.
.
I'm last line.
username@localhost:~/basiccommands$

```
<br>

Explore different [OPTIONS] that can be used with **tail** command(use `man tail` to see available [OPTIONS]).  

<br>

## 9. cat

**cat** stands for concatnate. It concatenates file(s) to standard output.

> cat [OPTIONS] FILE(s)


<p class="terminal">Terminal</p>
```
username@localhost:~/basiccommands$ cat newfile.txt
I'm first line.
I'm second line.
.
.
.
I'm last line.
username@localhost:~/basiccommands$

```
<br>

Use `-n or --number` to number the output lines.

<p class="terminal">Terminal</p>
```
username@localhost:~/basiccommands$ cat newfile.txt
1  I'm first line.
2  I'm second line.
3  I'm third line.
.   . 
.   . 
.   .
.   .
10 I'm last **line**.
username@localhost:~/basiccommands$

```
<br>

If you want to learn more about **cat** command, enter `man cat` in your terminal.  

<br>

