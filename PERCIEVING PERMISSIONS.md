# PERCIEVING PERMISSION 

**changing file ownership**

in this exercise we are going to learn about chown command
The decription is :
> First things first: file ownership. Every file in Linux is owned by a user on the system. Most often, in your day-to-day life, that user is the user you log in as every day.

On a shared system (such as in a computer lab), there might be many people with different user accounts, all with their own files in their own home directories. But even on a non-shared system (such as your personal PC), Linux still has many "service" user accounts for different tasks.

The two most important user accounts are:

Your user account! On pwn.college, this is the hacker user, regardless of what your username is.
root. This is the administrative account and, in most security situations, the ultimate prize. If you take over the root user, you've almost certainly achieved your hacking objective!
So what? Well, it turns out that the way that we prevent you from just doing cat /flag is by having /flag owned by the root user, configure its permissions so that no other user can read it (you will learn how to do that later), and configure the actual challenge to run as the root user (you will learn how to do this later as well). The result is that when you do cat /flag, you get:

hacker@dojo:~$ ls -l /flag
-r-------- 1 root root 53 Jul  4 04:47 /flag
hacker@dojo:~$ cat /flag
cat: /flag: Permission denied
hacker@dojo:~$
Here, you can see that the flag is owned by the root user (the first root in that line) and the root group (the second root in that line). When we try to read it as the hacker user, we are denied. However, if we were root (a hacker's dream!), we would have no problem reading this file:

root@dojo:~# cat /flag
pwn.college{demo_flag}
root@dojo:~#
Interestingly, we can change the ownership of files! This is done via the chown (change owner) command:

chown [username] [file]
Typically, chown can only be invoked by the root user. Let's pretend that we're root again (that never gets old!), and watch a typical use of chown:

root@dojo:~# mkdir pwn_directory
root@dojo:~# touch college_file
root@dojo:~# ls -l
total 4
-rw-r--r-- 1 root root    0 May 22 13:42 college_file
drwxr-xr-x 2 root root 4096 May 22 13:42 pwn_directory
root@dojo:~# chown hacker college_file
root@dojo:~# ls -l
total 4
-rw-r--r-- 1 hacker root    0 May 22 13:42 college_file
drwxr-xr-x 2 root   root 4096 May 22 13:42 pwn_directory
root@dojo:~#
college_file's owner has been changed to the hacker user, and how hacker can do with it whatever root had been able to do with it! If this was the /flag file, that means that the hacker user would be able to read it!


The exercsie is:
> In this level, we will practice changing the owner of the /flag file to the hacker user, and then the flag. For this challenge only, I made it so that you can use chown to your heart's content as the hacker user (again, typically, this requires you to be root). Use this power wisely and chown away!

* first we have to try running /flag file
* it says permission denieed
* so we have to change ownership for the file using the command chown hacker /flag
* now cat the file to get the flag

![image](https://github.com/user-attachments/assets/41ee7fed-21c8-4df9-bcdc-ee1aed078d95)





**GROUPS AND FILES**

IN this exercise we are going to learn how to change the group ownership with chgrp command 
The description is :

> Sharing is caring, and sharing is built into Linux's design. Files have both an owning user and group. A group can have multiple users in it, and a user can be a member of multiple groups.

You can check what groups you are part of with the id command:

hacker@dojo:~$ id
uid=1000(hacker) gid=1000(hacker) groups=1000(hacker)
hacker@dojo:~$
Here, the hacker user is only in the hacker group. The most common use-case for groups is to control access to different system resources. For example, "Practice Mode" in pwn.college grants you root access to allow better debugging and so on. This is handled by giving you an extra group when you launch in practice mode:

hacker@dojo:~$ id
uid=1000(hacker) gid=1000(hacker) groups=1000(hacker),27(sudo)
hacker@dojo:~$
A typical main user of a typical Linux desktop has a lot of groups. For example, this is Zardus' desktop:

zardus@yourcomputer:~$ id
uid=1000(zardus) gid=1000(zardus) groups=1000(zardus),24(cdrom),25(floppy),27(sudo),29(audio),30(dip),44(video),46(plugdev),100(users),106(netdev),114(bluetooth),117(lpadmin),120(scanner),995(docker)
zardus@yourcomputer:~$
All these groups give Zardus the ability to read CDs and floppy disks (who does that anymore?), administer the system, play music, draw to the video monitor, use bluetooth, and so on. Often, this access control happens via group ownership on the filesystem! For example, graphical output can be done via the special /dev/fb0 file:

zardus@yourcomputer:~$ ls -l /dev/fb0
crw-rw---- 1 root video 29, 0 Jun 30 23:42 /dev/fb0
zardus@yourcomputer:~$
This file is a special device file (type c means it is a "character device"), and interacting with it results in changes to the display output (rather than changes to disk storage, as for a normal file!). Zardus' user account on his machine can interact with it because the the file has a group ownership of video, and Zardus is a member of the video group.

No such luck for the /flag file in the dojo, though! Consider the following:

hacker@dojo:~$ id
uid=1000(hacker) gid=1000(hacker) groups=1000(hacker)
hacker@dojo:~$ ls -l /flag
-r--r----- 1 root root 53 Jul  4 04:47 /flag
hacker@dojo:~$ cat /flag
cat: /flag: Permission denied
hacker@dojo:~$
Here, the flag file is owned by the root user and the root group, and the hacker user is neither the root user nor a member of the root group, so the file cannot be accessed. Luckily, group ownership can be changed with the chgrp (change group) command! Unless you have write access to the file and membership in the new group, this typically requires root access, so let's check it out as root:

root@dojo:~# mkdir pwn_directory
root@dojo:~# touch college_file
root@dojo:~# ls -l
total 4
-rw-r--r-- 1 root root    0 May 22 13:42 college_file
drwxr-xr-x 2 root root 4096 May 22 13:42 pwn_directory
root@dojo:~# chgrp hacker college_file
root@dojo:~# ls -l
total 4
-rw-r--r-- 1 root hacker    0 May 22 13:42 college_file
drwxr-xr-x 2 root root   4096 May 22 13:42 pwn_directory
root@dojo:~#



The exercise is:
> In this level, I have made the flag readable by whatever group owns it, but this group is currently root. Luckily, I have also made it possible for you to invoke chgrp as the hacker user! Change the group ownership of the flag file, and read the flag!

* here first when we try to invole the /flag command it says permission denied
* so we have to use chgrp command with arguments hacker /flag
* now cat the /flag file to get the flag

![image](https://github.com/user-attachments/assets/e8f73ac5-e4fd-4234-b52c-2d3d5dca12b0)





**FUN WITH GROUP NAMES**

in this exercise we are going to learn  how to use id command 
The dezcription is:
> In the previous levels, you may have noticed that your hacker user is a member of the hacker group, and that zardus is a member of the zardus group. There is a convention in Linux that every user has their own group, but this does not have to be the case. For example, many computer labs will put all of their users into a single, shared users group.

The exercise is:
> The point is, you've used hacker for the group before, but in this level, that is not going to work. I'll still allow you to use chgrp, but I have randomized the name of the group that your user is in. You will need to use the id command to figure that name out, then chgrp to victory!

* first we have to see our user is in which group using id command
* then we have to chgrp with the argument with that group name /flag
* now cat the /flag file to get the flag

![image](https://github.com/user-attachments/assets/e4e09931-836f-40ff-99bf-e92dbc55b901)





**CHANGING PERMISSIONS**

In this exercise we are going to learn how to change permissions for group and other users 
The description is :
> So now we're well-versed in ownership. Let's talk about the other side of the coin: file permissions. Recall our example:

hacker@dojo:~$ mkdir pwn_directory
hacker@dojo:~$ touch college_file
hacker@dojo:~$ ls -l
total 4
-rw-r--r-- 1 hacker hacker    0 May 22 13:42 college_file
drwxr-xr-x 2 hacker hacker 4096 May 22 13:42 pwn_directory
hacker@dojo:~$
As a reminder, the first character there is the file type. The next nine characters are the actual access permissions of the file or directory, split into 3 characters denoting permissions for the owning user (now you understand this!), 3 characters denoting the permissions for the owning group (now you understand this as well!), and 3 characters denoting the permissions that all other access (e.g., by other users and other groups) has to the file.

Each character of the three represent permission for a different type:

r - user/group/other can read the file (or list the directory)
w - user/group/other can modify the files (or create/delete files in the directory)
x - user/group/other can execute the file as a program (or can enter the directory, e.g., using `cd`)
- - nothing 
For college_file above, the rw-r--r-- permissions entry decodes to:

r: the user that owns the file (user hacker) can read it
w: the user that owns the file (user hacker) can write to it
-: the user that owns the file (user hacker) cannot execute it
r: users in the group that owns the file (group hacker) can read it
-: users in the group that owns the file (group hacker) cannot write to it
-: users in the group that owns the file (group hacker) cannot execute it
r: all other users can read it
-: all other users cannot write to it
-: all other users cannot execute it
Now, let's look at the default permissions of /flag:

hacker@dojo:~$ ls -l /flag
-r-------- 1 root root 53 Jul  4 04:47 /flag
hacker@dojo:~$
Here, there is only one bit set: the read permission for the owning user (in this case, root). Members of the owning group (the root group) and all other users have no access to the file.

You might be wondering how the chgrp levels worked, if there is no group access to the file. Well, for those levels, I set the permissions differently:

hacker@dojo:~$ ls -l /flag
-r--r----- 1 root root 53 Jul  4 04:47 /flag
hacker@dojo:~$
The group had access! That is why chgrping the file enabled you to read the file.

Anyways! Like ownership, file permissions can also be changed. This is done with the chmod (change mode) command. The basic usage for chmod is:

chmod [OPTIONS] MODE FILE
You can specify the MODE in two ways: as a modification of the existing permissions mode, or as a completely new mode to overwrite the old one.

In this level, we will cover the former: modifying an existing mode. chmod allows you to tweak permissions with the mode format of WHO+/-WHAT, where WHO is user/group/other and WHAT is read/write/execute. For example, to add read access for the owning user, you would specify a mode of u+r. write and execute access for the group and the other (or all the modes) are specified the same way. More examples:

u+r, as above, adds read access to the user's permissions
g+wx adds write and execute access to the group's permissions
o-w removes write access for other users
a-rwx removes all permissions for the user, group, and world
So:

root@dojo:~# mkdir pwn_directory
root@dojo:~# touch college_file
root@dojo:~# ls -l
total 4
-rw-r--r-- 1 root root    0 May 22 13:42 college_file
drwxr-xr-x 2 root root 4096 May 22 13:42 pwn_directory
root@dojo:~# chmod go-rwx *
root@dojo:~# ls -l
total 4
-rw------- 1 hacker root    0 May 22 13:42 college_file
drwx------ 2 root   root 4096 May 22 13:42 pwn_directory
root@dojo:~#


The exercise is:
> In this challenge, you must change the permissions of the /flag file to read it! Typically, you need to have write access to the file in order to change its permissions, but I have made the chmod command all-powerful for this level, and you can chmod anything you want even though you are the hacker user. This is an ultimate power. The /flag file is owned by root, and you can't change that, but you can make it readable. Go and solve this!

* in this first we have to cat the /flag file
* then we will get that permission denied
* so now we have to use chmod command to change the mode to other user since we are other user
* so write the command go+rwx /flag  which enables read ,write and execute commands to the other users for this file
* now cat /flag to get the flag

![image](https://github.com/user-attachments/assets/479f3be0-2f37-467b-bb3b-404e5a05c5ef)





**EXECUTABLE FILES** 

In this exercise we are going to learn how to give xexcution permission to other users
The description is :
> So far, you have mostly been dealing with read permissions. This makes sense, because you have been making the /flag file readable to read it. In this level, we will explore execute permissions.

When you invoke a program, such as /challenge/run, Linux will only actually execute it if you have execute-access to the program file. Consider:

hacker@dojo:~$ ls -l /challenge/run
-rwxr-xr-x 1 root root    0 May 22 13:42 /challenge/run
hacker@dojo:~$ /challenge/run
Successfully ran the challenge!
hacker@dojo:~$
In this case, /challenge/run runs because it is executable by the hacker user. Because the file is owned by the root user and root group, this requires that the execute bit is set on the other permissions). If we remove these permissions, the execution will fail!

hacker@dojo:~$ chmod o-x /challenge/run
hacker@dojo:~$ ls -l /challenge/run
-rwxr-xr-- 1 root root    0 May 22 13:42 /challenge/run
hacker@dojo:~$ /challenge/run
bash: /challenge/run: Permission denied
hacker@dojo:~$

The exercise is :
> In this challenge, the /challenge/run program will give you the flag, but you must first make it executable! Remember your chmod, and get /challenge/run to tell you the flag!

* first we have to write a command ls -l /challenge/run to see the permissions given
* then we have to change the permissions with the command chmod ug+x /challenge/run
* now execute it to get the flag

![image](https://github.com/user-attachments/assets/ce6a4e8a-2fb8-4406-9b6f-83667c9325e7)





**PERMISSION TWEAKING PRACTICE**

This a challenge of multiple steps 
The steps that are performed is :
![image](https://github.com/user-attachments/assets/71b1efc2-33b0-40e0-9713-66ca2ad32150)

![image](https://github.com/user-attachments/assets/7085e430-b716-4cab-9e2f-e8fdbb953686)

![image](https://github.com/user-attachments/assets/df0a47b9-c0f3-4fa1-abf3-6fb22b99ccaf)

![image](https://github.com/user-attachments/assets/113ef6d4-1bf7-4a4c-86a9-a49b9868f7cf)

![image](https://github.com/user-attachments/assets/06647f3a-e15b-46cc-85a9-39b41c803701)

![image](https://github.com/user-attachments/assets/04024e40-e91d-4be5-ae3b-5293663fb90a)

![image](https://github.com/user-attachments/assets/7eab6489-a0ad-40ca-bb0c-d4dc60fc6d28)





**PERMISSION SETTING PRACTICE**

This a challenge of multiple steps 
The steps that are performed is :

![image](https://github.com/user-attachments/assets/3196999c-6121-480b-a462-10e38e53d39c)

![image](https://github.com/user-attachments/assets/892c9856-8199-463c-a2b6-dbbf0b8b4297)

![image](https://github.com/user-attachments/assets/ff3bd097-c049-4e29-836b-cf8a3a72cc25)

![image](https://github.com/user-attachments/assets/dede8c4a-3f75-4059-93bc-c3810bf85d34)

![image](https://github.com/user-attachments/assets/d5ac4402-c11c-472d-8d58-60bd5f500e32)

![image](https://github.com/user-attachments/assets/67f0c905-8945-40db-934d-37a5bf5e887f)





**THE SUID BIT**

The description on this exercsie is:
> There are many cases in which non-root users need elevated access to do certain system tasks. The system admin can't be there to give them the password every time a user wanted to do a task that only root/sudoers can do. The "Set User ID" (SUID) permissions bit allows the user to run a program as the owner of that program's file.

This is actually the exact mechanism used to let the challenge programs you run read the flag or, outside of pwn.college, to enable system administration tools such as su, sudo, and so on. The permission of a file with SUID list look like this:

hacker@dojo:~$ ls -l /usr/bin/sudo
-rwsr-xr-x 1 root root 232416 Dec 1 11:45 /usr/bin/sudo
hacker@dojo:~$
The s part in place of the executable bit means that the program is executable with SUID. It means that, regardless of what user runs the program (as long as they have executable permissions), the program will execute as the owner user (in this case, the root user).

As the owner of a file, you can set a file's SUID bit by using chmod:

chmod u+s [program]
But be careful! Giving the SUID bit to an executable owned by root can give attackers a possible attack vector to become root. You will learn more about this in the Program Misuse module.

The exrecise is:
> Now, we are going to let you add the SUID bit to the /challenge/getroot program in order to spawn a root shell for you to cat the flag yourself

* The steps we need to do are done below

![image](https://github.com/user-attachments/assets/71b655de-57fa-4569-93ae-75b70e19940a)

























