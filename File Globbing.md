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









