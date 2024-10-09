## DESCRIPTION
Previously, your relative path was "naked": it directly specified the directory to descend into from the current directory. In this level, we're going to explore more explicit relative paths.

In most operating systems, including Linux, every directory has two implicit entries that you can reference in paths: . and ... The first, ., refers right to the same directory, so the following absolute paths are all identical to each other:

- /challenge
- /challenge/.
- /challenge/./././././././././
- /./././challenge/././

The following relative paths are also all identical to each other:

- challenge
- ./challenge
- ./././challenge
- challenge/.
  
Of course, if your current working directory is /, the above relative paths are equivalent to the above absolute paths.

This challenge will get you using . in your relative paths. Get ready!

## APPROACH 

I entered root using cd /

![image](https://github.com/user-attachments/assets/38ae29bb-e298-431e-8b05-7147e1cfea54)
----
## DESCRIPTION
## APPROACH

This command [/challenge/run] will copy the files present in it to the /f directory 

![image](https://github.com/user-attachments/assets/fb221960-79ee-43e5-a111-d8ca1b7f0281)
----
## DESCRIPTION
In this level, we'll practice refering to paths using . a bit more. This challenge will need you to run it from the /challenge directory. Here, things get slightly tricky.

Linux explicitly avoids automatically looking in the current directory when you provide a "naked" path. Consider the following:

> hacker@dojo:~$ cd /challenge
> 
> hacker@dojo:/challenge$ run
> 
This will not invoke /challenge/run. This is actually a safety measure: if Linux searched the current directory for programs every time you entered a naked path, you could accidentally execute programs in your current directory that happened to have the same names as core system utilities! As a result, the above commands will yield the following error:

> bash: run: command not found
> 
We'll explore the mechanisms behind this concept later, but in this challenge, will learn how to explicitly use relative paths to launch run in this scenario. The way to do this is to tell Linux that you explicitly want to execute a program in the current directory, using . like in the previous levels. Give it a try now!
## APPROACH

![image](https://github.com/user-attachments/assets/bd72ed2d-c612-4a7c-b0cf-af1bd94bce3c)
--
## DESCRIPTION
Now you're familiar with the concept of referring to absolute paths and changing directories. If you put in absolute paths everywhere, then it really doesn't matter what directory you are in, as you likely found out in the previous three challenges.

However, the current working directory does matter for relative paths.

- A relative path is any path that does not start at root (i.e., it does not start with /).
- A relative path is interpreted relative to your current working directory (cwd).
- Your cwd is the directory that your prompt is currently located at.

This means how you specify a particular file, depends on where the terminal prompt is located.

Imagine we want to access some file located at /tmp/a/b/my_file.

- If my cwd is /, then a relative path to the file is tmp/a/b/my_file.
- If my cwd is /tmp, then a relative path to the file is a/b/my_file.
- If my cwd is /tmp/a/b/c, then a relative path to the file is ../my_file. The .. refers to the parent directory.

Let's try it here! You'll need to run /challenge/run using a relative path while having a current working directory of /. For this level, I'll give you a hint. Your relative path starts with the letter c 😊

## APPROACH
![image](https://github.com/user-attachments/assets/018d52c8-2cf0-4d20-8374-33ec14807c22)
--
## DESCRIPTION
The Linux filesystem has tons of directories with tons of files. You can navigate around directories by using the cd (change directory) command and passing a path to it as an argument, as so:

> hacker@dojo:~$ cd /some/new/directory
> 
> hacker@dojo:/some/new/directory$ cd /some/new/directory
> 
This affects the "current working directory" of your process (in this case, the bash shell). Each process has a directory in which it's currently hanging out. The reasons for this will become clear later in the module.

As an aside, now you can see what the ~ was in the prompt! It shows the current that your shell is located at.

This challenge will require you to execute the /challenge/run program from a specific path (which it will tell you). You'll need to cd to that directory before rerunning the challenge program. Good luck!
## APPROACH
![image](https://github.com/user-attachments/assets/a386bd50-42d4-431b-b28d-edf7cbf9fb96)
--
## DESCRIPTION
The Linux filesystem has tons of directories with tons of files. You can navigate around directories by using the cd (change directory) command and passing a path to it as an argument, as so:

> hacker@dojo:~$ cd /some/new/directory
> 
> hacker@dojo:/some/new/directory$ cd /some/new/directory
> 
This affects the "current working directory" of your process (in this case, the bash shell). Each process has a directory in which it's currently hanging out. The reasons for this will become clear later in the module.

As an aside, now you can see what the ~ was in the prompt! It shows the current that your shell is located at.

This challenge will require you to execute the /challenge/run program from a specific path (which it will tell you). You'll need to cd to that directory before rerunning the challenge program. Good luck!
## APPROACH
![image](https://github.com/user-attachments/assets/a4489976-025f-4d95-bc45-d0d26c941a26)
--
## DESCRIPTION
The Linux filesystem has tons of directories with tons of files. You can navigate around directories by using the cd (change directory) command and passing a path to it as an argument, as so:

> hacker@dojo:~$ cd /some/new/directory
> 
> hacker@dojo:/some/new/directory$ cd /some/new/directory
> 
This affects the "current working directory" of your process (in this case, the bash shell). Each process has a directory in which it's currently hanging out. The reasons for this will become clear later in the module.

As an aside, now you can see what the ~ was in the prompt! It shows the current that your shell is located at.

This challenge will require you to execute the /challenge/run program from a specific path (which it will tell you). You'll need to cd to that directory before rerunning the challenge program. Good luck!
## APPROACH 
![image](https://github.com/user-attachments/assets/463c8e67-de49-494d-af9a-4dcbbfd58da4)
--
## DESCRIPTION
Let's explore a slightly more complicated path! Except for in the previous level, challenges in pwn.college are in the challenge directory and the challenge directory is, in turn, right in the root directory (/). The path to the challenge the directory is, thus, /challenge. The name of the challenge program in this level is run, and it lives in the /challenge directory. Thus, the path to the run challenge program is /challenge/run.

This challenge again requires you to execute it by invoking its absolute path. You'll want to execute the run file that is in the challenge directory that is, in turn, in the / directory. If you invoke the challenge correctly, it will give you the flag. Good luck!
## APPROACH
![image](https://github.com/user-attachments/assets/04ee434b-9d26-4ba4-953c-4c20c314bcb0)
--
## DESCRIPTION
Alright, so the filesystem starts at /. Under that, there are a whole mess of other directories, configuration files, programs, and, most importantly, flags. In this level, we've added a program right in /, called pwn, that will give you the flag. All you need to do for this level is to invoke this program!

You can invoke a program by providing its path on the command line. In this case, you'll be giving the exact path, starting from /, so the path would be /pwn. This style of path, one that starts with the root directory, is referred to as an "absolute path".

Start the challenge, launch a terminal, invoke the pwn program using its absolute path, and Capture that Flag! Good luck!

## APPROACH 
<img width="1022" alt="image" src="https://github.com/user-attachments/assets/95523312-644c-4bbe-a0a8-56094a189d9d">
--
