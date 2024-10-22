# Chaining Commands


**CHAINING WITH SEMICOLONS**

in this exercise we are going to learn how to chain commands 
The description is :
> The easiest way to chain commands is ;. In most contexts, ; separates commands in a similar way to how Enter separates lines. So, this:
> ![image](https://github.com/user-attachments/assets/257585a3-2c00-4bb0-a245-fdc2e30beb92)
>
> Is roughly the same as this:
> ![image](https://github.com/user-attachments/assets/d730f2bf-66f4-4b3b-a103-4bdb3510c2d7)
>
> Basically, when you hit Enter, your shell executes your typed command and, after that command terminates, give you the prompt to input another command. The semicolon is analogous, just without the prompt and with you entering both commands before anything is executed.

The exercise is:
> Give it a try now! In this level, you must run /challenge/pwn and then /challenge/college, chaining them with a semicolon.

* we have to write the command /challenge/pwn; /challenge/college to get the flag

![image](https://github.com/user-attachments/assets/c32d3adf-7969-4332-90ce-003b3664e3a1)





**YOUR FIRST SHELL SCRIPT**
in this exercise :
> As you combine more and more commands to achieve complex effects, the length of the combined prompt quickly gets really annoying to deal with. When this happens, you can put these commands in a file, called a shell script, and run them by executing the file! For example, consider our semicolon technique:
> ![image](https://github.com/user-attachments/assets/9efa595e-ec02-407f-9274-4a902f8c1d56)
>
>![image](https://github.com/user-attachments/assets/a5723cfe-a59a-467a-a9e2-aea002aad277)
>
> You can see that the shell script executed both commands, creating and printing the pwn file.

The exercise is:
> Now, it's your turn! Same as last level, run /challenge/pwn and then /challenge/college, but this time in a shell script called x.sh, then run it with bash!

* here we have to write nano x.sh
* to get into the shell now write the comands to be run combined
* now save it
* and exit using ctrl+x
* now write bash x.sh to get the flag

![image](https://github.com/user-attachments/assets/d048bf9b-e58e-4fcb-b6d1-c320b7e180dc)





**REDIRECTING SCRIPT OUTPUT**

The exercise is :
> ![image](https://github.com/user-attachments/assets/0ae72749-5994-4114-8d6b-30e9dad9a686)

* now we have to do the same process done for above exercise
* and pipe the bash x.sh command with /challenge/solve to get the flag

![image](https://github.com/user-attachments/assets/b0e9aed6-b860-4e81-8ea3-bb8d997b1ed8)






**EXECUTABLE SHELL SCRIPTS**
The description is :
> You have written your first shell script, but calling it via bash script.sh is a pain. Why do you need that bash?

When you invoke bash script.sh, you are, of course launching the bash command with the script.sh argument. This tells bash to read its commands from script.sh instead of standard input, and thus your shell script is executed.

It turns out that you can avoid the need to manually invoke bash. If your shell script file is executable (recall File Permissions), you can simply invoke it via its relative or absolute path! For example, if you create script.sh in your home directory and make it executable, you can invoke it via /home/hacker/script.sh or ~/script.sh or (if your working directory is /home/hacker) ./script.sh.


The exercise is :
> Try that here! Make a shellscript that will invoke /challenge/solve, make it executable, and run it without explicitly invoking bash!

* first write a shell script with  /challenge/solve in it
* now grant its permission to execute using chmod u+rwx /home/hacker/y.sh
* now we can run directly the /home/hacker/y.sh to get the flag

![image](https://github.com/user-attachments/assets/2c117e7c-d2f8-4951-bd2f-d668c408911e)

















