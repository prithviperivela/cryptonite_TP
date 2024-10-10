# practicing piping 
**redirecting output
in this exercise we are going to learn avout the > keyword 
The points about this are:
> First, let's look at redirect stdout to files. You can accomplish this with the > character, as so:
> ![image](https://github.com/user-attachments/assets/f2fa4229-46e3-4a06-8932-4b2771f432a3)
> This will redirect the output of echo hi (which will be hi) to the file asdf. You can then use a program such as cat to output this file:
> ![image](https://github.com/user-attachments/assets/9c272964-6d3b-46ef-acc5-4df2a70d1500)

The exercise asks us to do:
>In this challenge, you must use this input redirection to write the word PWN (all uppercase) to the filename COLLEGE (all uppercase).

* first we are going to redirect the command which we are written in the terminal
* using > command we can do it
* so the command will be echo PWN > COLLEGE to get the flag

![image](https://github.com/user-attachments/assets/0ca457a7-1536-458c-b6af-8d967657a79a)





**redirecting more output
in this we   are  going to redirect the output 
> Aside from redirecting the output of echo, you can, of course, redirect the output of any command. In this level, /challenge/run will once more give you a flag, but only if you redirect its output to the file myflag. Your flag will, of course, end up in the myflag file!

  The exercise is:
  > You'll notice that /challenge/run will still happily print to your terminal, despite you redirecting stdout. That's because it communicates its instructions and feedback over standard error, and only prints the flag over standard out!


* Here first we have to redirect the command /challenge/run to myflag
* after that the flag  has been redirected to the file myflag
* now cat the myflag file to get the flag

![image](https://github.com/user-attachments/assets/9b31fa02-ba76-4656-975f-cdf291fd0455)





** Appending output
in this we are going to learn about the appending keyword
The keypoints are:
>A common use-case of output redirection is to save off some command results for later analysis. Often times, you want to do this in aggregate: run a bunch of commands, save their output, and grep through it later. In this case, you might want all that output to keep appending to the same file, but > will create a new output file every time, deleting the old contents.

You can redirect input in append mode using >> instead of >, as so:
>![image](https://github.com/user-attachments/assets/62fd47ae-0ca2-4c77-927f-58dbfd496c55)

The exercise is:
>To practice, run /challenge/run with an append-mode redirect of the output to the file /home/hacker/the-flag. The practice will write the first half of the flag to the file, and the second half to stdout if stdout is redirected to the file. If you properly redirect in append-mode, the second half will be appended to the first, but if you redirect in truncation mode (>), the second half will overwrite the first and you won't get the flag!

Go for it now!


* first we need to append the /challenge/run with /home/hacker/the-flag.
* now we need to append stdout  with  /home/hacker/the-flag
* now cat the  /home/hacker/the-flag  file to get thae flag

![image](https://github.com/user-attachments/assets/be788c19-5dd5-4b38-9a4c-9b5db18d6219)





** redirecting input
int this exercise we are going to learn about < command 
keypoints:
> Just like you can redirect output from programs, you can redirect input to programs! This is done using <, as so:
> ![image](https://github.com/user-attachments/assets/a6a22cfe-9dcd-4a9d-bbbf-5546df242959)

The exercise here is:
>You can do interesting things with a lot of different programs using input redirection! In this level, we will practice using /challenge/run, which will require you to redirect the PWN file to it and have the PWN file contain the value COLLEGE! To write that value to the PWN file, recall the prior challenge on output redirection from echo!

* here we need to write the command echo CHALLENGE > PWN
* And next /challenge/run < PWN to get the flag

![image](https://github.com/user-attachments/assets/d3c13399-c28c-49be-88e4-d7f01865b14a)





** grepping stored results
this is a exercise involving the knowledge of the previous exercise 
The exercise is:
> You know how to run commands, how to redirect their output (e.g., >), and how to search through the resulting file (e.g., grep). Let's put this together!

In preparation for more complex levels, we want you to:

Redirect the output of /challenge/run to /tmp/data.txt.
This will result in a hundred thousand lines of text, with one of them being the flag, in /tmp/data.txt.
Grep that for the flag!


* here first we need to redirect/challenge/run to /tmp/data.txt
* now we need to cat the /tmp/data.txt file along with grep with the argument pwn.college to get the flag

![image](https://github.com/user-attachments/assets/fed12ff3-c656-480c-acaa-b8dbc3cce266)





** grepping live output
in this exercise we are going to learn a few points about the |(pipe) operator
>It turns out that you can "cut out the middleman" and avoid the need to store results to a file, like you did in the last level. You can use this using the | (pipe) operator. Standard output from the command to the left of the pipe will be connected to (piped into) the standard input of the command to the right of the pipe. For example:
>![image](https://github.com/user-attachments/assets/113c05f6-0f4e-4d8d-8c57-83775a60fe64)

The exercise here is:
>Now try it for yourself! /challenge/run will output a hundred thousand lines of text, including the flag. Grep for the flag!

* here we need to invoke a command /challenge/run |grep pwn.college
* this will give you the flag

![image](https://github.com/user-attachments/assets/4f0ba79a-69b2-4c6a-9387-db2180be37a8)

![image](https://github.com/user-attachments/assets/8282f138-fbb2-4b86-b1e2-cfcf62d7f2ff)





** grepping errors
** duplicating piped data with tee















  



