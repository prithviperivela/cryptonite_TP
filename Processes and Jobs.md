# Processes and Jobs


**listing processes**
 in this exercise we are going to learn about how to use ps command process status
The keypoints are:

> First, we will learn to list running processes using the ps command. Depending on whom you ask, ps either stands for "process snapshot" or "process status", and it lists processes. By default, ps just lists the processes running in your terminal, which honestly isn't very useful:
>![image](https://github.com/user-attachments/assets/8958e121-94f4-4338-abad-7662968c7baf)
> In the above example, we have the shell (bash) and the ps process itself, and that's all that's running on that specific terminal. We also see that each process has a numerical identifier (the Process ID, or PID), which is a number that uniquely identifies every running process in a Linux environment. We also see the terminal on which the commands are running (in this case, the designation pts/0), and the total amount of cpu time that the process has eaten up so far (since these processes are very undemanding, they have yet to eat up even 1 second!).
> In the majority of cases, this is all that you'll see with a default ps. To make it useful, we need to pass a few arguments.
> As ps is a very old utility, its usage is a bit of a mess. There are two ways to specify arguments.

"Standard" Syntax: in this syntax, you can use -e to list "every" process and -f for a "full format" output, including arguments. These can be combined into a single argument -ef.

"BSD" Syntax: in this syntax, you can use a to list processes for all users, x to list processes that aren't running in a terminal, and u for a "user-readable" output. These can be combined into a single argument aux.

These two methods, ps -ef and ps aux result in slightly different, but cross-recognizable output.

Let's try it in the dojo:
> ![image](https://github.com/user-attachments/assets/ed79fe94-e480-4763-9df1-00c74df1ad94)




The exercise is:
> Anyways! Let's practice. In this level, I have once again renamed /challenge/run to a random filename, and this time made it so that you cannot ls the /challenge directory! But I also launched it, so can find it in the running process list, figure out the filename, and relaunch it directly for the flag! Good luck!

* first wwe have to write the command ps -ef
* now we can see a /challenge/24245-run-21973 file running
* by this we get to kno wthe file name
* now run the command /challenge/24245-run-21973 to get the flag

![image](https://github.com/user-attachments/assets/85d287be-a72a-4885-8773-cf9e6110c666)





**killing processes**

in this exercise we are going to learn how to terminate a process
 The keypoints are:
> You've launched processes, you've viewed processes, now you will learn to terminate processes! In Linux, this is done using the aggressively-named kill command. With default options (which is all we'll cover in this level), kill will terminate a process in a way that gives it a chance to get its affairs in order before ceasing to exist.
> Let's say you had a pesky sleep process (sleep is a program that simply hangs out for the number of seconds specified on the commandline, in this case, 1337 seconds) that you launched in another terminal, like so:
> ![image](https://github.com/user-attachments/assets/b56401b9-d6a8-489d-8d08-9ff1103a77f1)
>
> How do we get rid of it? You use kill to terminate it by passing the process identifier (the PID from ps) as an argument, like so:
> ![image](https://github.com/user-attachments/assets/ec1fbfbc-b203-4793-9d17-87df2580b994)

The exercise is:
>Now, it's time to terminate your first process! In this challenge, /challenge/run will refuse to run while /challenge/dont_run is running! You must find the dont_run process and kill it. If you fail, pwn.college will disavow all knowledge of your mission. Good luck.

* first we have to see the processes which are all running using ps command
* now see the pid of /challenge/dont_run
* now terminate it using kill comand with the pid as its argument
* now run /challenge/run for the flag

 
![image](https://github.com/user-attachments/assets/5feb1a6f-3507-4759-9408-a06ecd500436)





**INTERUPPTING PROCESSES**

in this exercise we are going to learn about 
The keypoints are :
> You've learned how to kill other processes with the kill command, but sometimes you just want to get rid of the process that's clogging up your terminal! Luckily, terminals have a hotkey for this: Ctrl-C (e.g., holding down the Ctrl key and pressing C) sends an "interrupt" to whatever application is waiting on input from the terminal and, typically, this causes the application to cleanly exit.

The exercise here is:
> Try it here! /challenge/run will refuse to give you the flag until you interrupt it. Good luck!

* first we have to  check /challenge/run
* then we get a command to exit the clogging process
* so use ctrl+c  command to terminate it
* then  we can get the flag

![image](https://github.com/user-attachments/assets/ee32c8ce-5809-42c0-b185-ecc66520aa51)





**SUSPENDING PROCESSES**

now we are going to learn how to suspend a processs
The keypoints are:
> You have learned to interrupt processes with Ctrl-C, but there are less drastic measures you can use to get your terminal back! You can suspend processes to the background with Ctrl-Z. In this level, we'll explore how this works and, in the next level, we'll figure out how to resume those suspended processes!

The exercise is:
> This level's run wants to see another copy of itself running and using the same terminal. How? Use the terminal to launch it, then suspend it, then launch another copy while the first is suspended!

* first we have to run the command /challenge/run
* now suspend the running program into background using ctrl+z command
* now again run /challenge/run to get the flag

![image](https://github.com/user-attachments/assets/24f1b1e7-c845-4f97-83f6-e3d41014039a)





**RESUMING PROCESSES**

in this exercise  we are going to learn about how to resume a suspended process
The description of this exercise is:
> Usually, when you suspend processes, you'll want to resume them at some point. Otherwise, why not just terminate them? To resume processes, your shell provides the fg command, a builtin that takes the suspended process, resumes it, and puts it back in the foreground of your terminal.


 The exercise is:
 > Go try it out! This challenge's run needs you to suspend it, then resume it. Good luck!


* first run the command /challenge/run
* then  we have to suspend the /challenge/run  using ctrl+z command
* now resume it using fg command

![image](https://github.com/user-attachments/assets/ec7787c7-85df-4f82-add1-8d655428c944)





**BACKGOUNDING PROCESSES**








