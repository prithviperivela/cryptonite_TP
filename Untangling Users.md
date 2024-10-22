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
> ![image](https://github.com/user-attachments/assets/29d18409-f927-4464-891c-db7a4f041644)
>
> This check against the root password is what obsoletes su. Modern systems very rarely have root passwords, and different mechanisms (that we will learn later) are used to grant administrative access.

The exercise is:
> But THIS challenge (and only this challenge) does have a root password. That password is hack-the-planet, and you must provide it to su to become root! Go do that, and read the flag!

* first we need to write the command su
* then the shell asks for password type it
* then you will get the root shell now run the command cat /flag to get the flag

![image](https://github.com/user-attachments/assets/e5338a08-74a5-4fab-b8e3-ccecfba5d22a)





**OTHER USES WITH SU**

in this exercises we are going to cover other uses  of su command
The description is :
> With no arguments, su will start a root shell (after authenticating with root's password). However, you can also give a username as an argument to switch to that user instead of root. For example:
> ![image](https://github.com/user-attachments/assets/95650e8f-642e-4e31-befe-6cb091c38d5f)

The exrcise is:
> Awesome! In this level, you must switch to the zardus user and then run /challenge/run. Zardus' password is dont-hack-me. Good luck!

* first we have to write su command with argument zardus
* so as to get the zardus user shell
* write the password given
* now run /challenge/run
* to get the flag

![image](https://github.com/user-attachments/assets/2bd1b9cf-ab07-4cf0-a6d8-4d316dd7ce39)





**CRACKING PASSWORDS**

in this exercise we are going to learen how to crack password 
The description is :
> When you enter a password for su, it compares it against the stored password for that user. These passwords used to be stored in /etc/passwd, but because /etc/passwd is a globally-readable file, this is not good for passwords, these were moved to /etc/shadow. Here is the example /etc/shadow from the previous level:
> ![image](https://github.com/user-attachments/assets/8169b205-c9ae-42f5-bd98-92b1e7250012)
>
> Separated by :s, the first field of each line is the username and the second is the password. A value of * or ! functionally means that password login for the account is disabled, a blank field means that there is no password (a not-uncommon misconfiguration that allows password-less su in some configurations), and the long string such as Zardus' $6$bEFkpM0w/6J0n979$47ksu/JE5QK6hSeB7mmuvJyY05wVypMhMMnEPTIddNUb5R9KXgNTYRTm75VOu1oRLGLbAql3ylkVa5ExuPov1. is the result of one-way-encrypting (hashing) Zardus' password from the last level (in this case, dont-hack-me). Other fields in this file have other meanings, and you can read more about them here.
> When you input a password into su, it one-way-encrypts (hashes) it and compares the result against the stored value. If the result matches, su grants you access to the user!
> But what if you don't know the password? If you have the hashed value of the password, you can crack it! Even though /etc/shadow is, by default, only readable by root, leaks can happen! For example, backups are often stored, unencrypted and insufficiently protected, on file servers, and this has led to countless data disclosures.
> If a hacker gets their hands on a leaked /etc/shadow, they can start cracking passwords and wreaking havoc. The cracking can be done via the famous John the Ripper, as so:
> ![image](https://github.com/user-attachments/assets/b5fcfeb8-b2eb-4819-9c15-cdc2f520b3b2)

The exercise is:
> Here, John the Ripper cracked Zardus' leaked password hash to find the real value of password1337. Poor Zardus!

This level simulates this story, giving you a leak of /etc/shadow (in /challenge/shadow-leak). Crack it (this could take a few minutes), su to zardus, and run /challenge/run to get the flag!


* first we have to cat the /challenge/shadow-leak file to get the hash password of the zardus user
* then using john command o the file will give yo the normal password
* now using su command on the zardus with the found password
* gives you the zardus shell now run /challenge/run to get the flag

![image](https://github.com/user-attachments/assets/2bd2270b-6efb-45aa-b03b-3c86287e5d79)

![image](https://github.com/user-attachments/assets/6e763df2-12b9-4a11-9703-4fd634355fed)





**USING SUDO**

in this exercise we are goingto learn how to use sudo comand 
The description is :
> In the olden days, a typical Linux system had a root password that administrators would use to su to root (after logging into their account with their normal account password). But root passwords are a pain to maintain, they (or their hashes!) can leak, and they don't lend themselves well to larger environments (e.g., fleets of servers). To address this, in recent decades, the world has moved from administration via su to administration via sudo (superuser do).

Unlike su, which defaults to launching a shell as a specified user, sudo defaults to running a command as root:

hacker@dojo:~$ whoami
hacker
hacker@dojo:~$ sudo whoami
root
hacker@dojo:~$
Or, more relevant to getting flags:

hacker@dojo:~$ grep hacker /etc/shadow
grep: /etc/shadow: Permission denied
hacker@dojo:~$ sudo grep hacker /etc/shadow
hacker:$6$Xro.e7qB3Q2Jl2sA$j6xffIgWn9xIxWUeFzvwPf.nOH2NTWNJCU5XVkPuONjIC7jL467SR4bXjpVJx4b/bkbl7kyhNquWtkNlulFoy.:19921:0:99999:7:::
hacker@dojo:~$
Also unlike su, rather than authenticating via password, sudo relies on policies that it checks to determine the user's authorization run things as root. These policies are defined in /etc/sudoers, and though it's mostly out of scale for our purposes, there are plenty of resources for learning about this!

So, the world has moved to sudo and has (for the purposes of system administration) left su behind. In fact, even pwn.college's Practice Mode works by giving you sudo access to elevate privileges!


The exercise is:
> In this level, we will give you sudo access, and you will use it to read the flag. Nice and easy!

* we have cat the /flag file tpo get the flag
* but we need to be root to get it
* so we need to sudo cat /flag to get the flag

![image](https://github.com/user-attachments/assets/880f3ad8-70ce-4429-86cb-c9186379db6f)










