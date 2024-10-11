# File Globbing

** matching with *
In this exercise we are going to learn about the * keyword
points about this are:
>The first glob we'll learn is *. When it encounters a * character in any argument, the shell will treat it as "wildcard" and try to replace that argument with any files that match the pattern. It's easier to show you than explain:
>![image](https://github.com/user-attachments/assets/bf8e6525-0149-4b4a-8024-ad9a60721724)
>Of course, though in this case, the glob resulted in multiple arguments, it can just as simply match only one. For example:
>![image](https://github.com/user-attachments/assets/c5364c0d-3fc5-4b71-9e0a-a1831294b2d3)
>When zero files are matched, by default, the shell leaves the glob unchanged:
>![image](https://github.com/user-attachments/assets/ae4d22d8-4324-4729-8458-b8181e0206f2)
>The * matches any part of the filename except for / or a leading . character. For example:
>![image](https://github.com/user-attachments/assets/c633823a-b2e6-48ed-8c05-9be4ab54c13f)

The exiercise is:
>Now, practice this yourself! Starting from your home directory, change your directory to /challenge, but use globbing to keep the argument you pass to cd to at most four characters! Once you're there, run /challenge/run for the flag!

* here we need to invoke the command cd with * replacing the characters of challenge directory
* we should use cd to max fourletters
* so we invoke it as cd cha*
* after that run the command /challenge/run for the file

![image](https://github.com/user-attachments/assets/96d29050-8d4d-433f-b851-3fed81121580)





**matching with ?
Thi is the exercise telling about the ? keyword
keypoints:
>Next, let's learn about ?. When it encounters a ? character in any argument, the shell will treat it as single-character wildcard. This works like *, but only matches one character. For example:
>![image](https://github.com/user-attachments/assets/0dcdcf8d-aa60-42d9-be4c-530d39299f0f)

The exercise is:
>Now, practice this yourself! Starting from your home directory, change your directory to /challenge, but use the ? character instead of c and l in the argument to cd! Once you're there, run /challenge/run for the flag!

* it is same as doing the previous exercise 
* but as ? can only replace one character 
* replace all c and l with ?
* and run /challenge/run

![image](https://github.com/user-attachments/assets/c0378c4a-4749-4d5f-8277-ec57232092d0)





**matching with []
In this exercise we are going to learn about he [] keyword
The keypoints are:
>Next, we will cover []. The square brackes are, essentially, a limited form of ?, in that instead of matching any character, [] is a wildcard for some subset of potential characters, specified within the brackets. For example, [pwn] will match the character p, w, or n. For example:
>![image](https://github.com/user-attachments/assets/19da353c-b637-449b-a30c-8ee6b2ea723d)

The exercise is:
>Try it here! We've placed a bunch of files in /challenge/files. Change your working directory to /challenge/files and run /challenge/run with a single argument that bracket-globs into file_b, file_a, file_s, and file_h!

* here as the exercise say we need to to go to the /challenge/file directory first
* after that run the command /challenge/run with argument file_[bash}
* then we will get the flag

![image](https://github.com/user-attachments/assets/53363069-5b2d-42b3-9716-156205304987)





**matching paths with []

* the command for this exercise is:
* /challenge/run /challenge/files/file_[bash]

![image](https://github.com/user-attachments/assets/e04539be-c02f-4710-b1d4-b933e0106e2c)





** mixing globs
* the command is  cd /challenge/files
* /challenge/run [cep]*
![image](https://github.com/user-attachments/assets/4d6a193a-ee0d-4ba9-a84e-cb2e0745d709)





** exclusionary globbing
* the command here is cd /challenge/files
* now /challenge/run [pwn]* 
![image](https://github.com/user-attachments/assets/e8295a96-542d-486b-b6cb-a3b5ed967e91)








 













