Let's try something more complicated: a command with arguments, which is what we call additional data passed to the command. When you type a line of text and hit enter, the shell actually parses your input into a command and its arguments. The first word is the command, and the subsequent words are arguments. Observe:
>hacker@dojo:~$ echo Hello
>
>Hello
>
>hacker@dojo:~$
>
In this case, the command was echo, and the argument was Hello. echo is a simple command that "echoes" all of its arguments back out onto the terminal, like you see in the session above.

Let's look at echo with multiple arguments:

>hacker@dojo:~$ echo Hello Hackers!
>
>Hello Hackers!
>
>hacker@dojo:~$
>
In this case, the command was echo, and Hello and Hackers! were the two arguments to echo. Simple!
In this challenge, to get the flag, you must run the hello command (NOT the echo command) with a single argument of hackers. Try it now!

## APPROACH

![image](https://github.com/user-attachments/assets/79468952-dfa3-4e11-9b5d-fa1d9ef92dbe)





## DESCRIPTION
In this challenge, you will invoke your first command! When you type a command and hit enter, the command will be invoked, as so:

>hacker@dojo:~$ whoami
>
>hacker
>
>hacker@dojo:~$

Here, the user executed the whoami command, which simply prints the username (hacker) to the terminal. When the command terminates, the shell once again displays the prompt, ready for the next command.
In this level, invoke the *hello* command to get the flag! Keep in mind: commands in Linux are case sensitive: hello is different from HELLO.

## APPROACH
I opened the GUI DESKTOP Workspace provided when I click on START.
Then i opened the terminal and i entered the command whoami, to know in which user is currently logged in.  
And as mentioned i entered the hello command which gave me the flag. 

<img width="863" alt="image" src="https://github.com/user-attachments/assets/edcae25c-c098-46ca-a8c0-5d7b62e3e052">

