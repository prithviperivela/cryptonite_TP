# Untangling Users

**becoming root with su**

in this exercise we are going to learn about su command 
The description is:
> In the previous level, you used the /challenge/getroot program to become the root user. Becoming root is a fairly common action that Linux users take, and your typical Linux installation obviously does not have /challenge/getroot. Instead, there are two utilities used for this purposes: su and sudo.

In this challenge, we will cover the older one, su (the switch user command). This is not typically used to elevate to root access anymore, but it is an elegant utility from a more civilized time, and we'll cover it first.

su is a setuid binary:
> ![image](https://github.com/user-attachments/assets/9a7aedec-3460-46fd-9c06-1eef6d834fb7)
>
> Because it has the SUID bit set, su runs as root. Running as root, it can start a root shell! Of course, su is discerning: before allowing the user to elevate privileges to root, it checks to make sure that the user knows the root password:
> 




