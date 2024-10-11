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




** redirecting error 
in this exercise we are going to learn about redirecting errors 
Keypoints are:
> Just like standard output, you can also redirect the error channel of commands. Here, we'll learn about File Descriptor numbers. A File Descriptor (FD) is a number the describes a communication channel in Linux. You've already been using them, even though you didn't realize it. We're already familiar with three:

FD 0: Standard Input
FD 1: Standard Output
FD 2: Standard Error
When you redirect process communication, you do it by FD number, though some FD numbers are implicit. For example, a > without a number implies 1>, which redirects FD 1 (Standard Output). Thus, the following two commands are equivalent:

hacker@dojo:~$ echo hi > asdf
hacker@dojo:~$ echo hi 1> asdf
Redirecting errors is pretty easy from this point. If you have a command that might produce data via standard error (such as /challenge/run), you can do:

hacker@dojo:~$ /challenge/run 2> errors.log
That will redirect standard error (FD 2) to the errors.log file. Furthermore, you can redirect multiple file descriptors at the same time! For example:

hacker@dojo:~$ some_command > output.log 2> errors.log
That command will redirect output to output.log and errors to errors.log.


The exercise is to :
> Let's put this into practice! In this challenge, you will need to redirect the output of /challenge/run, like before, to myflag, and the "errors" (in our case, the instructions) to instructions. You'll notice that nothing will be printed to the terminal, because you have redirected everything! You can find the instructions/feedback in instructions and the flag in myflag when you successfully pull this off!


* here we have to write the command /challenge /run  > myflag 2> instructions
* in this command the first half is redirecting the output of the  command to myflag file
* the second half is redirecting the errors to the instructions file
* now cat the myflag file to get the flag

![WhatsApp Image 2024-10-11 at 2 44 54 PM](https://github.com/user-attachments/assets/48a549e5-22ca-4ce8-9c38-5ba945d05258)




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

int this exercise we are going to learn  about grepping the errors
keypoints are:
>You know how to redirect errors to a file, and you know how to pipe output to another program, such as grep. But what if you wanted to grep through errors directly?
>The > operator redirects a given file descriptor to a file, and you've used 2> to redirect fd 2, which is standard error. The | operator redirects only standard output to another program, and there is no 2| form of the operator! It can only redirect standard output (file descriptor 1).
>The shell has a >& operator, which redirects a file descriptor to another file descriptor. This means that we can have a two-step process to grep through errors: first, we redirect standard error to standard output (2>& 1) and then pipe the now-combined stderr and stdout as normal (|)!

the exercise is:
>Try it now! Like the last level, this level will overwhelm you with output, but this time on standard error. Grep through it to find the flag!

* we need to write the command /challenge/run 2>&1 | grep pwn.college
* the first half is to redirect the output and error
* and then grep the flag in the output and the flag
* combining these two commands using pipe operator

![image](https://github.com/user-attachments/assets/df9597a2-2ecf-47a3-a5a6-9449f3f931aa)





** duplicating piped data with tee

keypoints of this exercise are:
>When you pipe data from one command to another, you of course no longer see it on your screen. This is not always desired: for example, you might want to see the data as it flows through between your commands to debug unintended outcomes (e.g., "why did that second command not work???").

Luckily, there is a solution! The tee command, named after a "T-splitter" from plumbing pipes, duplicates data flowing through your pipes to any number of files provided on the command line. For example:
>![image](https://github.com/user-attachments/assets/3fc45565-530b-4b76-b658-ed119f75a64d)
>
>As you can see, by providing two files to tee, we ended up with three copies of the piped-in data: one to stdout, one to the pwn file, and one to the college file. You can imagine how you might use this to debug things going haywire:
>
>![image](https://github.com/user-attachments/assets/13fdd7cb-fbc4-4efe-a603-544961565a06)

The exercise here is:
>Now, you try it! This process' /challenge/pwn must be piped into /challenge/college, but you'll need to intercept the data to see what pwn needs from you!

* for this we need to write the command /challenge/pwn | tee output.txt | /challenge/college
* thyen you will get the instruction that the /challenge/pwn is missing an argument that need to be passed
* for that you need to cat the text in which you are duplicatingthe first command
* now run the commands using the pipe

![image](https://github.com/user-attachments/assets/2bf470b6-70ee-4719-a778-45847e96618e)

![image](https://github.com/user-attachments/assets/69778a65-ebd3-4940-831f-a8f16af4dbaf)





** writing to multiple programs

> Linux follows the philosophy that "everything is a file". This is, the system strives to provide file-like access to most resources, including the input and output of running programs! The shell follows this philosophy, allowing you to, for example, use any utility that takes file arguments on the command line (such as tee) and hook it up to the input or output side of a program!

> This is done using what's called Process Substitution. If you write an argument of >(rev), bash will run the rev command (this command reads data from standard input, reverses its order, and writes it to standard output!), but hook up its input to a temporary file that it will create. This isn't a real file, of course, it's what's called a named pipe

![image](https://github.com/user-attachments/assets/af8f0917-227c-4be9-93c7-ea946932452d)





** split-piping stderr and stdout
Now, let's put your knowledge together. You must master the ultimate piping task: redirect stdout to one program and stderr to another.

The challenge here, of course, is that the | operator links the stdout of the left command with the stdin of the right command. Of course, you've used 2>&1 to redirect stderr into stdout and, thus, pipe stderr over, but this then mixes stderr and stdout. How to keep it unmixed?

You will need to combine your knowledge of >(), 2>, and |. How to do it is a task I'll leave to you.

In this challenge, you have:


* command is
* /challenge/hack > >(/challenge/planet) 2> >(/challenge/the)

![image](https://github.com/user-attachments/assets/4fa41c3b-8730-40f1-9a25-1fb25e0a9d02)


       

















  



