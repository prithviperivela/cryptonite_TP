#Pondering PATH

**THE PATH VARIABLE**

This exercise tells us about the PATH variable 
Keypoints are:
> It turns out that the answer to "How does the shell find ls?" is fairly simple. There is a special shell variable, called PATH, that stores a bunch of directory paths in which the shell will search for programs corresponding to commands. If you blank out the variable, things go badly:
> ![image](https://github.com/user-attachments/assets/b24415ff-e0b0-40c7-8aa8-8e39f49cb963)
> 
> Without a PATH, bash cannot find the ls command.

The exercise is:
> In this level, you will disrupt the operation of the /challenge/run program. This program will DELETE the flag file using the rm command. However, if it can't find the rm command, the flag will not be deleted, and the challenge will give it to you! Thus, you must make it so that /challenge/run also can't find the rm command!

* for this we have to se PATH variable to null like this PATH=" "
* now run the /challenge/run command as it cannot find rm command it gives you the flag

![image](https://github.com/user-attachments/assets/450e0c81-0088-4472-84af-77fddf1dddcf)





**SETTING PATH**
![image](https://github.com/user-attachments/assets/75724680-351b-4bf4-afaf-1f9426ca82f9)

The exercise is:
> Let's practice. This level's /challenge/run will run the win command via its bare name, but this command exists in the /challenge/more_commands/ directory, which is not initially in the PATH. The win command is the only thing that /challenge/run needs, so you can just overwrite PATH with that one directory. Good luck!


* here we have to set the PATH to /challenge/more_commands
* then run /challenge/run to get the flag

![image](https://github.com/user-attachments/assets/d141d4dc-286e-4d63-acfe-91b452dd3324)





**ADDING COMMANDS**
KEYPOINTS:
> ![image](https://github.com/user-attachments/assets/e764dc61-5dfb-4b3c-88ad-c6524458307a)

The exercise is:
> Previously, the win command that /challenge/run executed was stored in /challenge/more_commands. This time, win does not exist! Recall the final level of Chaining Commands, and make a shell script called win, add its location to the PATH, and enable /challenge/run to find it!

* 









