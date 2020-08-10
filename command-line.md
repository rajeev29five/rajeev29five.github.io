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

## 1. ls[![link](assets/images/link_icon.svg)](#1-ls)

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

## 2. mkdir[![link](assets/images/link_icon.svg)](#2-mkdir)

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

## 3. cd[![link](assets/images/link_icon.svg)](#3-cd)

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

## 4. pwd[![link](assets/images/link_icon.svg)](#4-pwd)

**pwd** stands for "print working directory", it prints absolute pathname of the current working directory. 

<p class="terminal">Terminal</p>
```
username@localhost:~/basiccommands$ pwd
/home/username/basiccommands
username@localhost:~/basiccommands$


```
<br>

## 5. touch[![link](assets/images/link_icon.svg)](#5-touch)

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

## 6. chmod[![link](assets/images/link_icon.svg)](#6-chmod)

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

## 7. head[![link](assets/images/link_icon.svg)](#7-head)

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

## 8. tail[![link](assets/images/link_icon.svg)](#8-tail)

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

## 9. cat[![link](assets/images/link_icon.svg)](#9-cat)

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
10 I'm last line.
username@localhost:~/basiccommands$

```
<br>

If you want to learn more about **cat** command, enter `man cat` in your terminal.  

<br>

## 10. grep[![link](assets/images/link_icon.svg)](#10-grep)

**grep** stands for global regular expression print. It searches for PATTERN in each file and prints the matching line.

> grep [OPTIONS] PATTERN FILE(s)

<p class="terminal">Terminal</p>
<div class="highlighter-rouge"><pre class="highlight"><code>username@localhost:~/basiccommands$ grep "second" newfile.txt
I'm <span class="colbol">second</span> line.
username@localhost:~/basiccommands$<br/>
</code></pre></div>
<br>

`-n` or `--line-number` prefixes each line of output with 1-based numbering.
<p class="terminal">Terminal</p>
<div class="highlighter-rouge"><pre class="highlight"><code>username@localhost:~/basiccommands$ grep -n "second" newfile.txt
<strong>2: </strong>I'm <span class="colbol">second</span> line.
username@localhost:~/basiccommands$<br/>
</code></pre></div>
<br>

`-i` or `--ignore-case` matches pattern in the file irrespective of case distinctions(upper or lower case). Change any letter that you want search to uppercase in **newfile.txt**. For example I am changing **second** to **SECOND** in newfile.txt. 
<p class="terminal">Terminal</p>
<div class="highlighter-rouge"><pre class="highlight"><code>username@localhost:~/basiccommands$ grep "second" -i newfile.txt<br/>I'm <span class="colbol">SECOND</span> line.<br/>username@localhost:~/basiccommands$<br/>
</code></pre></div>
<br>

## 11. rm[![link](assets/images/link_icon.svg)](#11-rm)

**rm** stands for remove. It removes files or directories.

> rm [OPTIONS] FILE(s)


<p class="terminal">Terminal</p>
```
username@localhost:~/basiccommands$ rm file.txt
username@localhost:~/basiccommands$

```
<br>

`-r` or `--recursive` removes directories and their contents recursively.

<p class="terminal">Terminal</p>
```
username@localhost:~/basiccommands$ rm -r directory/
username@localhost:~/basiccommands$

```

<br>

## 12. mv[![link](assets/images/link_icon.svg)](#12-mv)

**mv** stands for move. It moves or renames files or directories.

> mv FILE DESTINATION

<p class="terminal">Terminal</p>
```
username@localhost:~/basiccommands$ mv oldname.txt newname.txt
username@localhost:~/basiccommands$ mv oldname_dir newname_dir
username@localhost:~/basiccommands$

```
<br>

To move a file or a directory to an other directory you have to do like that :

<p class="terminal">Terminal</p>
```
username@localhost:~/basiccommands$ mv newname.txt newname_dir/
username@localhost:~/basiccommands$

```
<br>

## 13. history[![link](assets/images/link_icon.svg)](#13-history)

**history** shows a list of the command entered since the session began.

> history OPTIONS

<p class="terminal">Terminal</p>
<div class="highlighter-rouge">
    <pre class="highlight"><code>username@localhost:~/basiccommands$ history<br>   1  ls<br>   2  cd<br>   3  pwd
    </code></pre>
</div>
<br>

`history #` displays the latest # commands from history

<p class="terminal">Terminal</p>
<div class="highlighter-rouge">
    <pre class="highlight"><code>username@localhost:~/basiccommands$ history 2<br>   1  ls<br>   2  cd
    </code></pre>
</div>
<br>

`!#` repeats the #th command from history

<p class="terminal">Terminal</p>
<div class="highlighter-rouge">
    <pre class="highlight"><code>username@localhost:~/basiccommands$ !3<br>pwd<br>/home/username/basiccommands
    </code></pre>
</div>
<br>

`!!` repeats the most recent command from history

<p class="terminal">Terminal</p>
<div class="highlighter-rouge">
    <pre class="highlight"><code>username@localhost:~/basiccommands$ !!<br>pwd<br>/home/username/basiccommands
    </code></pre>
</div>
<br>


`history -d #` deletes the numbered line from history

<p class="terminal">Terminal</p>
<div class="highlighter-rouge">
    <pre class="highlight"><code>username@localhost:~/basiccommands$ history -d 3<br>username@localhost:~/basiccommands$
    </code></pre>
</div>
<br>

`history -c` deletes the numbered line from history

<p class="terminal">Terminal</p>
<div class="highlighter-rouge">
    <pre class="highlight"><code>username@localhost:~/basiccommands$ history -c<br>username@localhost:~/basiccommands$ 
    </code></pre>
</div>
<br>

## 14. last command

**last**
This command is used to display the list of all the users to logged into our computer system. 

`last`
<p class="terminal">Terminal</p>
```
username@localhost:~/basiccommands$ last
```
<br>

```
Output:

uddeshya :0           :0               Mon Aug 10 08:26   still logged in
reboot   system boot  5.4.0-42-generic Mon Aug 10 08:25   still running
uddeshya :0           :0               Sun Aug  9 19:45 - 21:44  (01:58)
reboot   system boot  5.4.0-42-generic Sun Aug  9 19:44 - 21:44  (01:59)
uddeshya :0           :0               Sun Aug  9 14:39 - 16:14  (01:35)
reboot   system boot  5.4.0-42-generic Sun Aug  9 14:38 - 16:14  (01:36)
uddeshya :0           :0               Sun Aug  9 11:27 - 12:31  (01:03)
reboot   system boot  5.4.0-42-generic Sun Aug  9 11:26 - 12:31  (01:04)
uddeshya :0           :0               Sun Aug  9 08:13 - 09:54  (01:40)
reboot   system boot  5.4.0-42-generic Sun Aug  9 08:12 - 09:54  (01:42)
uddeshya :0           :0               Sat Aug  8 13:44 - 15:29  (01:45)
reboot   system boot  5.4.0-42-generic Sat Aug  8 13:43 - 15:29  (01:45)
uddeshya :0           :0               Sat Aug  8 10:16 - 11:51  (01:34)
reboot   system boot  5.4.0-42-generic Sat Aug  8 10:15 - 11:51  (01:35)
uddeshya :0           :0               Sat Aug  8 07:40 - 08:46  (01:06)
reboot   system boot  5.4.0-42-generic Sat Aug  8 07:39 - 08:46  (01:07)
uddeshya :0           :0               Fri Aug  7 19:09 - down   (01:26)
reboot   system boot  5.4.0-42-generic Fri Aug  7 19:08 - 20:35  (01:27)
uddeshya :0           :0               Fri Aug  7 17:00 - down   (00:56)
reboot   system boot  5.4.0-42-generic Fri Aug  7 16:59 - 17:56  (00:56)
uddeshya :0           :0               Fri Aug  7 12:12 - 13:34  (01:21)
reboot   system boot  5.4.0-42-generic Fri Aug  7 12:11 - 13:34  (01:22)
uddeshya :0           :0               Fri Aug  7 09:09 - down   (00:35)
reboot   system boot  5.4.0-42-generic Fri Aug  7 09:08 - 09:44  (00:36)
uddeshya :0           :0               Thu Aug  6 19:50 - 21:34  (01:43)
reboot   system boot  5.4.0-42-generic Thu Aug  6 19:49 - 21:34  (01:45)
uddeshya :0           :0               Thu Aug  6 17:43 - 18:18  (00:34)
reboot   system boot  5.3.0-62-generic Thu Aug  6 17:42 - 18:18  (00:35)
uddeshya :0           :0               Thu Aug  6 09:51 - 13:18  (03:26)
reboot   system boot  5.3.0-62-generic Thu Aug  6 09:49 - 13:18  (03:28)
uddeshya :0           :0               Wed Aug  5 18:52 - 20:00  (01:07)
reboot   system boot  5.3.0-62-generic Wed Aug  5 18:51 - 20:00  (01:08)
uddeshya :0           :0               Wed Aug  5 13:43 - 17:15  (03:32)
reboot   system boot  5.3.0-62-generic Wed Aug  5 13:42 - 17:15  (03:33)
uddeshya :0           :0               Wed Aug  5 08:10 - 11:37  (03:27)
reboot   system boot  5.3.0-62-generic Wed Aug  5 08:09 - 11:37  (03:28)
uddeshya :0           :0               Tue Aug  4 20:23 - 21:50  (01:27)
reboot   system boot  5.3.0-62-generic Tue Aug  4 20:22 - 21:50  (01:28)
uddeshya :0           :0               Tue Aug  4 16:07 - 17:34  (01:27)
reboot   system boot  5.3.0-62-generic Tue Aug  4 16:06 - 17:36  (01:29)
uddeshya :0           :0               Tue Aug  4 11:58 - 14:58  (02:59)
reboot   system boot  5.3.0-62-generic Tue Aug  4 11:58 - 14:58  (03:00)
uddeshya :0           :0               Mon Aug  3 19:26 - down   (00:27)
reboot   system boot  5.3.0-62-generic Mon Aug  3 19:25 - 19:54  (00:28)
uddeshya :0           :0               Mon Aug  3 11:43 - 12:44  (01:00)
reboot   system boot  5.3.0-62-generic Mon Aug  3 11:42 - 12:44  (01:01)
uddeshya :0           :0               Mon Aug  3 07:36 - 08:16  (00:40)
reboot   system boot  5.3.0-62-generic Mon Aug  3 07:35 - 08:16  (00:41)
uddeshya :0           :0               Sun Aug  2 19:55 - 22:13  (02:17)
reboot   system boot  5.3.0-62-generic Sun Aug  2 19:54 - 22:13  (02:18)
uddeshya :0           :0               Sun Aug  2 13:01 - down   (02:16)
reboot   system boot  5.3.0-62-generic Sun Aug  2 13:00 - 15:17  (02:17)
uddeshya :0           :0               Sun Aug  2 08:10 - 08:55  (00:45)
reboot   system boot  5.3.0-62-generic Sun Aug  2 08:09 - 08:55  (00:46)
uddeshya :0           :0               Sat Aug  1 12:16 - 12:51  (00:34)
reboot   system boot  5.3.0-62-generic Sat Aug  1 12:12 - 12:51  (00:38)

wtmp begins Sat Aug  1 10:06:19 2020
```

<br>

`last -5`
The flag -5 will only dispaly last 5 users who were logged into the system 

<p class="terminal">Terminal</p>
```
username@localhost:~/basiccommands$ last -5
```
<br>
```
Output:

uddeshya :0           :0               Mon Aug 10 08:26   still logged in
reboot   system boot  5.4.0-42-generic Mon Aug 10 08:25   still running
uddeshya :0           :0               Sun Aug  9 19:45 - 21:44  (01:58)
reboot   system boot  5.4.0-42-generic Sun Aug  9 19:44 - 21:44  (01:59)
uddeshya :0           :0               Sun Aug  9 14:39 - 16:14  (01:35)

```

<br>

 
`last -R basil`
This will hide the host field name 

<p class="terminal">Terminal</p>
```
username@localhost:~/basiccommands$ last -R basil
```
<br>
```
Output:

wtmp begins Sat Aug  1 10:06:19 2020
```

<br>

`last -F`
This command will displaythe login and logout time with their respective dates

<p class="terminal">Terminal</p>
```
username@localhost:~/basiccommands$ last -F
```
<br>
```
Output:

uddeshya :0           :0               Mon Aug 10 08:26:46 2020   still logged in
reboot   system boot  5.4.0-42-generic Mon Aug 10 08:25:42 2020   still running
uddeshya :0           :0               Sun Aug  9 19:45:51 2020 - Sun Aug  9 21:44:18 2020  (01:58)
reboot   system boot  5.4.0-42-generic Sun Aug  9 19:44:37 2020 - Sun Aug  9 21:44:24 2020  (01:59)
uddeshya :0           :0               Sun Aug  9 14:39:33 2020 - Sun Aug  9 16:14:40 2020  (01:35)
reboot   system boot  5.4.0-42-generic Sun Aug  9 14:38:34 2020 - Sun Aug  9 16:14:47 2020  (01:36)
uddeshya :0           :0               Sun Aug  9 11:27:50 2020 - Sun Aug  9 12:31:21 2020  (01:03)
reboot   system boot  5.4.0-42-generic Sun Aug  9 11:26:48 2020 - Sun Aug  9 12:31:24 2020  (01:04)
uddeshya :0           :0               Sun Aug  9 08:13:25 2020 - Sun Aug  9 09:54:23 2020  (01:40)
reboot   system boot  5.4.0-42-generic Sun Aug  9 08:12:23 2020 - Sun Aug  9 09:54:26 2020  (01:42)
uddeshya :0           :0               Sat Aug  8 13:44:30 2020 - Sat Aug  8 15:29:30 2020  (01:45)
reboot   system boot  5.4.0-42-generic Sat Aug  8 13:43:35 2020 - Sat Aug  8 15:29:34 2020  (01:45)
uddeshya :0           :0               Sat Aug  8 10:16:44 2020 - Sat Aug  8 11:51:14 2020  (01:34)
reboot   system boot  5.4.0-42-generic Sat Aug  8 10:15:39 2020 - Sat Aug  8 11:51:32 2020  (01:35)
uddeshya :0           :0               Sat Aug  8 07:40:39 2020 - Sat Aug  8 08:46:45 2020  (01:06)
reboot   system boot  5.4.0-42-generic Sat Aug  8 07:39:39 2020 - Sat Aug  8 08:46:49 2020  (01:07)
uddeshya :0           :0               Fri Aug  7 19:09:25 2020 - down                      (01:26)
reboot   system boot  5.4.0-42-generic Fri Aug  7 19:08:25 2020 - Fri Aug  7 20:35:45 2020  (01:27)
uddeshya :0           :0               Fri Aug  7 17:00:36 2020 - down                      (00:56)
reboot   system boot  5.4.0-42-generic Fri Aug  7 16:59:39 2020 - Fri Aug  7 17:56:36 2020  (00:56)
uddeshya :0           :0               Fri Aug  7 12:12:36 2020 - Fri Aug  7 13:34:24 2020  (01:21)
reboot   system boot  5.4.0-42-generic Fri Aug  7 12:11:30 2020 - Fri Aug  7 13:34:27 2020  (01:22)
uddeshya :0           :0               Fri Aug  7 09:09:14 2020 - down                      (00:35)
reboot   system boot  5.4.0-42-generic Fri Aug  7 09:08:00 2020 - Fri Aug  7 09:44:31 2020  (00:36)
uddeshya :0           :0               Thu Aug  6 19:50:42 2020 - Thu Aug  6 21:34:41 2020  (01:43)
reboot   system boot  5.4.0-42-generic Thu Aug  6 19:49:38 2020 - Thu Aug  6 21:34:46 2020  (01:45)
uddeshya :0           :0               Thu Aug  6 17:43:36 2020 - Thu Aug  6 18:18:29 2020  (00:34)
reboot   system boot  5.3.0-62-generic Thu Aug  6 17:42:39 2020 - Thu Aug  6 18:18:33 2020  (00:35)
uddeshya :0           :0               Thu Aug  6 09:51:45 2020 - Thu Aug  6 13:18:44 2020  (03:26)
reboot   system boot  5.3.0-62-generic Thu Aug  6 09:49:52 2020 - Thu Aug  6 13:18:48 2020  (03:28)
uddeshya :0           :0               Wed Aug  5 18:52:50 2020 - Wed Aug  5 20:00:12 2020  (01:07)
reboot   system boot  5.3.0-62-generic Wed Aug  5 18:51:45 2020 - Wed Aug  5 20:00:15 2020  (01:08)
uddeshya :0           :0               Wed Aug  5 13:43:46 2020 - Wed Aug  5 17:15:51 2020  (03:32)
reboot   system boot  5.3.0-62-generic Wed Aug  5 13:42:01 2020 - Wed Aug  5 17:15:54 2020  (03:33)
uddeshya :0           :0               Wed Aug  5 08:10:20 2020 - Wed Aug  5 11:37:38 2020  (03:27)
reboot   system boot  5.3.0-62-generic Wed Aug  5 08:09:21 2020 - Wed Aug  5 11:37:40 2020  (03:28)
uddeshya :0           :0               Tue Aug  4 20:23:35 2020 - Tue Aug  4 21:50:36 2020  (01:27)
reboot   system boot  5.3.0-62-generic Tue Aug  4 20:22:19 2020 - Tue Aug  4 21:50:38 2020  (01:28)
uddeshya :0           :0               Tue Aug  4 16:07:33 2020 - Tue Aug  4 17:34:47 2020  (01:27)
reboot   system boot  5.3.0-62-generic Tue Aug  4 16:06:40 2020 - Tue Aug  4 17:36:18 2020  (01:29)
uddeshya :0           :0               Tue Aug  4 11:58:58 2020 - Tue Aug  4 14:58:04 2020  (02:59)
reboot   system boot  5.3.0-62-generic Tue Aug  4 11:58:05 2020 - Tue Aug  4 14:58:08 2020  (03:00)
uddeshya :0           :0               Mon Aug  3 19:26:22 2020 - down                      (00:27)
reboot   system boot  5.3.0-62-generic Mon Aug  3 19:25:27 2020 - Mon Aug  3 19:54:09 2020  (00:28)
uddeshya :0           :0               Mon Aug  3 11:43:50 2020 - Mon Aug  3 12:44:25 2020  (01:00)
reboot   system boot  5.3.0-62-generic Mon Aug  3 11:42:54 2020 - Mon Aug  3 12:44:28 2020  (01:01)
uddeshya :0           :0               Mon Aug  3 07:36:06 2020 - Mon Aug  3 08:16:25 2020  (00:40)
reboot   system boot  5.3.0-62-generic Mon Aug  3 07:35:10 2020 - Mon Aug  3 08:16:27 2020  (00:41)
uddeshya :0           :0               Sun Aug  2 19:55:45 2020 - Sun Aug  2 22:13:25 2020  (02:17)
reboot   system boot  5.3.0-62-generic Sun Aug  2 19:54:50 2020 - Sun Aug  2 22:13:28 2020  (02:18)
uddeshya :0           :0               Sun Aug  2 13:01:44 2020 - down                      (02:16)
reboot   system boot  5.3.0-62-generic Sun Aug  2 13:00:44 2020 - Sun Aug  2 15:17:54 2020  (02:17)
uddeshya :0           :0               Sun Aug  2 08:10:19 2020 - Sun Aug  2 08:55:35 2020  (00:45)
reboot   system boot  5.3.0-62-generic Sun Aug  2 08:09:05 2020 - Sun Aug  2 08:55:37 2020  (00:46)
uddeshya :0           :0               Sat Aug  1 12:16:20 2020 - Sat Aug  1 12:51:14 2020  (00:34)
reboot   system boot  5.3.0-62-generic Sat Aug  1 12:12:56 2020 - Sat Aug  1 12:51:18 2020  (00:38)

wtmp begins Sat Aug  1 10:06:19 2020

```

<br>

`last -a`
This command will put the host column to the very last

<p class="terminal">Terminal</p>
```
username@localhost:~/basiccommands$ last -a
```
<br>
```
Output:

uddeshya :0           Mon Aug 10 08:26   still logged in    :0
reboot   system boot  Mon Aug 10 08:25   still running      5.4.0-42-generic
uddeshya :0           Sun Aug  9 19:45 - 21:44  (01:58)     :0
reboot   system boot  Sun Aug  9 19:44 - 21:44  (01:59)     5.4.0-42-generic
uddeshya :0           Sun Aug  9 14:39 - 16:14  (01:35)     :0
reboot   system boot  Sun Aug  9 14:38 - 16:14  (01:36)     5.4.0-42-generic
uddeshya :0           Sun Aug  9 11:27 - 12:31  (01:03)     :0
reboot   system boot  Sun Aug  9 11:26 - 12:31  (01:04)     5.4.0-42-generic
uddeshya :0           Sun Aug  9 08:13 - 09:54  (01:40)     :0
reboot   system boot  Sun Aug  9 08:12 - 09:54  (01:42)     5.4.0-42-generic
uddeshya :0           Sat Aug  8 13:44 - 15:29  (01:45)     :0
reboot   system boot  Sat Aug  8 13:43 - 15:29  (01:45)     5.4.0-42-generic
uddeshya :0           Sat Aug  8 10:16 - 11:51  (01:34)     :0
reboot   system boot  Sat Aug  8 10:15 - 11:51  (01:35)     5.4.0-42-generic
uddeshya :0           Sat Aug  8 07:40 - 08:46  (01:06)     :0
reboot   system boot  Sat Aug  8 07:39 - 08:46  (01:07)     5.4.0-42-generic
uddeshya :0           Fri Aug  7 19:09 - down   (01:26)     :0
reboot   system boot  Fri Aug  7 19:08 - 20:35  (01:27)     5.4.0-42-generic
uddeshya :0           Fri Aug  7 17:00 - down   (00:56)     :0
reboot   system boot  Fri Aug  7 16:59 - 17:56  (00:56)     5.4.0-42-generic
uddeshya :0           Fri Aug  7 12:12 - 13:34  (01:21)     :0
reboot   system boot  Fri Aug  7 12:11 - 13:34  (01:22)     5.4.0-42-generic
uddeshya :0           Fri Aug  7 09:09 - down   (00:35)     :0
reboot   system boot  Fri Aug  7 09:08 - 09:44  (00:36)     5.4.0-42-generic
uddeshya :0           Thu Aug  6 19:50 - 21:34  (01:43)     :0
reboot   system boot  Thu Aug  6 19:49 - 21:34  (01:45)     5.4.0-42-generic
uddeshya :0           Thu Aug  6 17:43 - 18:18  (00:34)     :0
reboot   system boot  Thu Aug  6 17:42 - 18:18  (00:35)     5.3.0-62-generic
uddeshya :0           Thu Aug  6 09:51 - 13:18  (03:26)     :0
reboot   system boot  Thu Aug  6 09:49 - 13:18  (03:28)     5.3.0-62-generic
uddeshya :0           Wed Aug  5 18:52 - 20:00  (01:07)     :0
reboot   system boot  Wed Aug  5 18:51 - 20:00  (01:08)     5.3.0-62-generic
uddeshya :0           Wed Aug  5 13:43 - 17:15  (03:32)     :0
reboot   system boot  Wed Aug  5 13:42 - 17:15  (03:33)     5.3.0-62-generic
uddeshya :0           Wed Aug  5 08:10 - 11:37  (03:27)     :0
reboot   system boot  Wed Aug  5 08:09 - 11:37  (03:28)     5.3.0-62-generic
uddeshya :0           Tue Aug  4 20:23 - 21:50  (01:27)     :0
reboot   system boot  Tue Aug  4 20:22 - 21:50  (01:28)     5.3.0-62-generic
uddeshya :0           Tue Aug  4 16:07 - 17:34  (01:27)     :0
reboot   system boot  Tue Aug  4 16:06 - 17:36  (01:29)     5.3.0-62-generic
uddeshya :0           Tue Aug  4 11:58 - 14:58  (02:59)     :0
reboot   system boot  Tue Aug  4 11:58 - 14:58  (03:00)     5.3.0-62-generic
uddeshya :0           Mon Aug  3 19:26 - down   (00:27)     :0
reboot   system boot  Mon Aug  3 19:25 - 19:54  (00:28)     5.3.0-62-generic
uddeshya :0           Mon Aug  3 11:43 - 12:44  (01:00)     :0
reboot   system boot  Mon Aug  3 11:42 - 12:44  (01:01)     5.3.0-62-generic
uddeshya :0           Mon Aug  3 07:36 - 08:16  (00:40)     :0
reboot   system boot  Mon Aug  3 07:35 - 08:16  (00:41)     5.3.0-62-generic
uddeshya :0           Sun Aug  2 19:55 - 22:13  (02:17)     :0
reboot   system boot  Sun Aug  2 19:54 - 22:13  (02:18)     5.3.0-62-generic
uddeshya :0           Sun Aug  2 13:01 - down   (02:16)     :0
reboot   system boot  Sun Aug  2 13:00 - 15:17  (02:17)     5.3.0-62-generic
uddeshya :0           Sun Aug  2 08:10 - 08:55  (00:45)     :0
reboot   system boot  Sun Aug  2 08:09 - 08:55  (00:46)     5.3.0-62-generic
uddeshya :0           Sat Aug  1 12:16 - 12:51  (00:34)     :0
reboot   system boot  Sat Aug  1 12:12 - 12:51  (00:38)     5.3.0-62-generic

wtmp begins Sat Aug  1 10:06:19 2020

```
