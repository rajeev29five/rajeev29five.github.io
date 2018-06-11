---
layout: default
---
---

## What is a Terminal?

A terminal is text-based application used for viewing, manipulating and handling files on your computer. It can be considered as Windows' File Explorer or Mac's Finder without a graphical interface. It is also known as **CLI, command line, console, prompts**. 

This is what a prompt looks like on linux system.

```
username@localhost~$
```

A prompt has four parts.

`username : `  Shows the username. 

`hostname : `  This is the name of your computer.

`absolutepathname : ` Shows the absolute path name of current working directory. In this case it is **home** directory represented by the symbol tilde(~).

`currentuser : ` The shell prompt normally ends in a **$** sign which means that the user is logged in as normal user with restricted access to resources, while **#** indicates that you are logged in as **root** also know as **super user** and can access nearly all resources which is other wise accessible to few programs. 

**NOTE :** You should avoid logging in as root unless necessary as it makes your system vulnerable.

## 1. mkdir

**mkdir** stands for make directory. A directory is a folder. Command creates directory(ies), if they do not already exist.

**mkdir** takes the following form.

> mkdir _OPTIONS_ nameOfDirectory

```
example
```

## 2. ls

**ls** stands for list. Lists the contents of directory(files and subdirectory(ies)) with additional information. 

**ls** takes the following form.

> ls _OPTIONS_ namofDirectory
 
```
example
```

## 3. touch

An empty file that does not exist is created.

**touch** takes the following form.

> touch _OPTIONS_ nameOfFile

```
example
```

## 4. cd

**cd** stands for change directory. Used to traverse directory(ies). If name of directory is not supplied, working directory is changed to root or home. If **`..`** is supplied, working directory is set to immediate previous of current working directory. If **`-`** is supplied old working directory is set to current working directory, if the directory change is successful, the absolute pathname of the new working directory is written to the standard  output.

```
example
```

## 5. pwd

**pwd** prints absolute pathname of the current working directory. 


```
example
```


## 6. chmod



```
example
```


## 7. head


Prints the first 10 lines of each file to standard output. In case more than one file is specified, standard output of each file is preceded by header giving the file name. If **`-n`** or **`--lines`** is supplied, then **`n`** number of lines are printed to standard output.


```
example
```


## 8. tail

**tail** prints the last 10 lines of each file to standard output. In case more than one file is specified, standard output of each file is preceded by header giving the file name. If **`-n`** or **`--lines`** is supplied, then **n** number of lines are printed to standard output.


```
example
```
