# comprehending_commands
**cat :not the pet ,but the command

> cat is a most important command in linux .
> One of the most critical Linux commands is cat. cat is most often used for reading out files
> cat will concatenate (hence the name) multiple files if provided multiple arguments


The exercise here says that:
> In this challenge, I will copy the flag to the flag file in your home directory (where your shell starts). Go read it with cat!

* here since he said that flag is in the home directory where the shell starts we write ls commands to see what all files are there in the directory in which we are in there we can see a file name flag so hence by using cat command we cn read the flag file for flag.
![Screenshot 2024-10-08 132252](https://github.com/user-attachments/assets/10c6b936-7424-4510-b56f-9e4192f173b7)



**catting absolute paths

>In the last level, you did cat flag to read the flag out of your home directory! You can, of course, specify cat's arguments as absolute paths


The exercises here says that 
>In this directory, I will not copy it to your home directory, but I will make it readable. You can read it with cat at its absolute path: /flag.


* here it is said that e flag is in another directory and gave its absolutepath so by using cat command on the absolutepath gives us the flag .

![a](https://github.com/user-attachments/assets/9235b846-ddcb-4940-a183-60d7f93c688a)





**more catting practice

The exercise here says that :
>You can specify all sorts of paths as arguments to commands, and we'll practice some more with cat. In this level, I'll put the flag in some crazy directory, and I will not allow you to change directories with cd, so no cat flag for you. You must retrieve the flag by absolute path, wherever it is.


*in this exercise when we open the VS-code workspace 
we can see a instruction diplayed in the terminal like this: 
![image](https://github.com/user-attachments/assets/04a689e9-4a56-4a84-9a7f-dd072f8f17dd)

*by looking at the instruction we can understand that the flag is in the directory that is specified in the instruction 
*so by using cat command to the absolutepath provided in the instruction will give us te flag.


![image](https://github.com/user-attachments/assets/fec0c374-9d21-4e55-9e67-2f6cdfc440e6)





**grepping for a needle in a haystack

in this exercise we are going to learn about the grep command 
>this takes us to the question where we actually use the grep command
>Sometimes, the files that you might cat out are too big. Luckily, we have the grep command to search for the contents we need!
>now the next question that arises is how to use it for that there is an example given in the exerise that is
>There are many ways to grep, and we'll learn on way here:

>![image](https://github.com/user-attachments/assets/35673684-a5fc-4c50-afa5-15e24783509a)
>Invoked like this, grep will search the file for lines of text containing SEARCH_STRING and print them to the console.


The exercise here says that :
>In this challenge, I've put a hundred thousand lines of text into the /challenge/data.txt file. Grep it for the flag!
>and it also gave us a hint
>HINT: The flag always starts with the text pwn.college.


* from the exercise we get to know that the flag is in the absolutepath /challenge/data.txt
* but it also specifies that the file which we cat contains alot of text and the fag is in it somewhere
* so we can understand that to find the flag we need to use grep command
* but now the question is that what argument should we provide to find the flag
* now we can make use of the hint where it says that the flag always starts with the text pwn.college.
* so now by using cat command on the  absolute path provided along with the grep command with the argument pwn.college gives us the flag

![image](https://github.com/user-attachments/assets/5748f190-74a8-40c3-b779-3a6113a25125)
*note the symbol '|'which we used in between the two commands is used to link two commands





**listing files 
in this exercise we are going to learn aout the ls command are :
The points that the exercise tells about ls command are
>So far, we've told you which files to interact with. But directories can have lots of files (and other directories) inside them, and we won't always be here to tell you their names. You'll need to learn to list their contents using the ls command!
>ls will list files in all the directories provided to it as arguments, and in the current directory if no arguments are provided. Observe:
>![image](https://github.com/user-attachments/assets/df135bae-261d-45ff-930a-63fccd8593ea)

The exercise here says that :
>In this challenge, we've named /challenge/run with some random name! List the files in /challenge to find it.

* here from the information given in the exercise it is said that  theyhave named the ?challenge?run with some random name
* we know that /challenge/run would give us the flag so they are saying that the name of the file which give us the flag has been renamed to some other name
* so to find it we have to ls command on /challenge directory
* when we do so we find two directories inside it
* those are:24555-renamed-run-29126 and  DESCRIPTION.md
* we can assume that the flag is in the 1st file as we can say that the 2nd file is a markdownfile whichcontains the desvription of the challenge
* so by writing the command /challenge/24555-renamed-run-29126 we can get the flag

![image](https://github.com/user-attachments/assets/c0ee3bab-0c10-437f-82eb-e5393858be09)





**touching files
in this exercise we are going to learn about the touch command 
The points that this exercise tells us about the touch command are :
>Of course, you can also create files! There are several ways to do this, but we'll look at a simple command here. You can create a new, blank file by touching it with the touch command:
>![image](https://github.com/user-attachments/assets/da8ecd90-e4cd-4949-a6c2-51067053721f)

The exercise here says that :
>It's that simple! In this level, please create two files: /tmp/pwn and /tmp/college, and run /challenge/run to get your flag!

* it is a simple exercise it says us to create two files in the tmp directory using touch command
* so first we use touch command to create a file /temp/pwn
* again we use the touch command to create a file /temp/challenge
* now we will execute the command /challenge/run in order to get the flag

![image](https://github.com/user-attachments/assets/4fa3331e-1ac9-421e-89a6-fc024b58d470)





**removing files








   














