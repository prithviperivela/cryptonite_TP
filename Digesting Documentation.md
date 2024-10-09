# Digesting documentation
** learning from documentation
in  this exercise we are going to learn about how to invoke arguments prorperly but in a basic way 
The points that are mentioned about this in the exercise are:
>The typical need you'll have for documentation is just to figure out how to use all these dang programs, and a specific case of that is figuring out what arguments to specify on the command line. This module will mostly dig into that concept, as a proxy for figuring out how to use the programs in general. Through the rest of the module, you'll go through various ways of asking the environment for help for the programs, but first, we'll dig into the concept of reading documentation.

The correct usage of programs depends, in a large part, in the proper specification of arguments to them. Recall the -a of ls -a in the hidden files challenge of the Basic Commands module: that -a was an argument that told ls to list out hidden files as well as non-hidden files. Because we wanted to list out hidden files, invoking ls with the -a argument was the correct way to use it in our scenario.


This exercise asks us to do :
>The program for this challenge is /challenge/challenge, and you'll need to invoke it properly in order for it to give you the flag. Let's pretend that this is its documentation:
The documentation is:
>![image](https://github.com/user-attachments/assets/e2bc06f1-79d4-48e0-bfa1-a26908b96657)

* for this we need to invoke the command with the argument mentioned in the documentation
* so the command will be /challenge/challenge --giveflag
* by running the abov command we will get the flag

![image](https://github.com/user-attachments/assets/a4117dee-bc45-4bd1-8595-978f4155eebd)





** learning complex usage
This exercise here is about learning anout giving complex arguments:
the description about this that are given are:
>While using most commands is straightforward, the usage of some commands can get quite complex. For example, the arguments to commands like sed and awk, which we're definitely not getting into right now, are entire programs in an esoteric programming language! Somewhere on the spectrum between cd and awk are commands that take arguments to their arguments...

This sounds crazy, but you've already encountered this with the find level in Basic Commands. find has a -name argument, and the -name argument itself takes an argument specifying the name to search for. Many other commands are analogous.


The decription that is provided to this exercise is:
>Here is this level's documentation for /challenge/challenge:
>![image](https://github.com/user-attachments/assets/141cf52c-0430-44b4-b8a4-5bdc9f0f2326)


* here as the exercise says that we need to invoke argument --printfile  for the command /challengelchallenge command
* again the --printfile needs to be given the location of the flag as the argument
* so hence the command would be /challenge/challenge --printfile /flag
* by invoking the above command we can get the flag

![image](https://github.com/user-attachments/assets/8cef4f22-a41a-40b4-b6a5-03cd98e1a80c)





** reading manuals   
in this exercise we are going to learn about the man command 
The points that are given about this command are:
>This level introduces the man command. man is short for manual, and will display (if available) the manual of the command you pass as an argument. For example, let's say we wanted to learn about the yes command (yes, this is a real command):
>![image](https://github.com/user-attachments/assets/f3895c69-833e-4573-a1c8-8cd7b4383d70)
>This will display the manual page for yes, which will look something like this:
>![image](https://github.com/user-attachments/assets/3ce3b89e-63c8-44ff-8aa3-e46534684a99)
>![image](https://github.com/user-attachments/assets/400e80b8-f35d-4342-86d9-27e2eb67a246)
>The important sections are:
>![image](https://github.com/user-attachments/assets/c241ddab-9378-476b-b79a-25efb21252e8)
>You can scroll around the manpage with your arrow keys and PgUp/PgDn. When you're done reading the manpage, you can hit q to quit.

Manpages are stored in a centralized database. If you're curious, this database lives in the /usr/share/man directory, but you never need to interact with it directly: you just query it using the man command. The arguments to the man command aren't file paths, but just the names of the entries themselves (e.g., you run man yes to look up the yes manpage, rather than man /usr/bin/yes, which would be the actual path to the yes program but would result in man displaying garbage).

This exercise aks us to do:
>The challenge in this level has a secret option that, when you use it, will cause the challenge to print the flag. You must learn this option through the man page for challenge!


* here first we need to read the manual of the challenge command using the man command
* after getting the manual we can see name as /challenge/challenge command can print flag but with proper arguments
* the proper argument can be found in the description which is   --wczqal NUM
* in place of NUM we need to write 097 to invoke the command
* and hence we can get the flag

![image](https://github.com/user-attachments/assets/1a9fb912-6cd8-4833-a5a0-f1e62c1e8fe1)
![image](https://github.com/user-attachments/assets/3cef6b13-d4c0-4322-b30d-4fcbaa67b0b0)





** searching manuals 
in this exercise we are going to learn how to find something in the manual of a command
The points regarding this exercise are:
>You can scroll man pages with the arrow keys (and PgUp/PgDn) and search with /. After searching, you can hit n to go to the next result and N to go to the previous result. Instead of /, you can use ? to search backwards!

The exercise asks us to do:
>Find the option that will give you the flag by reading the challenge man page.

* first we need to get the manual for the challenge command
* inorder to get it we need to use the cammand man with argument challenge
* now in the description we need to find the argument which gives us the flag with the command in the nam /challenge/challenge
* to find it write /flag command it searches the text file in the description
* to get the next result of the search use n
* and finally you will find the argument
* write the argument along with the command /challenge/challenge to get the flag

![image](https://github.com/user-attachments/assets/38590095-3f20-4a04-ac32-0f94c5f4500a)





** searching for manuals
This exercise is a challenge involving the man command :
>This level is tricky: it hides the manpage for the challenge by randomizing its name. Luckily, all of the man pages are gathered in a searchable database, so you'll be able to search the man page database to find the hidden challenge man page! To figure out how to search for the right man page, read the man page manpage by doing: man man!
>the hints given to this are
>HINT 1: man man teaches you advanced usage of the man command itself, and you must use this knowledge to figure out how to search for the hidden manpage that will tell you how to use /challenge/challenge

>HINT 2: though the man page is randomly named, you still actually use /challenge/challenge to get the flag!




** help for builtins
in this exercise we are going to learn about he help command 
The points regarding help commands are:
>Some commands, rather than being programs with man pages and help options, are built into the shell itself. These are called builtins. Builtins are invoked just like commands, but the shell handles them internally instead of launching other programs. You can get a list of shell builtins by running the builtin help, as so:
>![image](https://github.com/user-attachments/assets/b2dea387-7f6a-4bd5-ba90-6f71b516d194)


The challenge here is:
>Some good information! In this challenge, we'll practice using help to look up help for builtins. This challenge's challenge command is a shell builtin, rather than a program. Like before, you need to lookup its help to figure out the secret value to pass to it!

* here first we need to argument the builtin challenge to the help command
* where we get few arguments to find the flag
* by seeng those we can find the argument
* and then use the command challenge argument t get the flag

![image](https://github.com/user-attachments/assets/c9822bbe-7b59-480f-a151-62f6f95bc617)


  






 







