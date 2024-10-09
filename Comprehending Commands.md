# comprehending_commands
**cat :not the pet ,but the command

> cat is a most important command in linux .
> One of the most critical Linux commands is cat. cat is most often used for reading out files
> cat will concatenate (hence the name) multiple files if provided multiple arguments


The exercise here says that:
> In this challenge, I will copy the flag to the flag file in your home directory (where your shell starts). Go read it with cat!

* here since he said that flag is in the home directory where the shell starts we write ls commands to see what all files are there in the directory in which we are in there we can see a file name flag so hence by using cat command we cn read the flag file for flag.
![Screenshot 2024-10-08 132252](https://github.com/user-attachments/assets/10c6b936-7424-4510-b56f-9e4192f173b7)



**catting absolute paths

>In the last level, you did cat flag to read the flag out of your home directory! You can, of course, specify cat's arguments as absolute paths


The exercises here says that 
>In this directory, I will not copy it to your home directory, but I will make it readable. You can read it with cat at its absolute path: /flag.


* here it is said that e flag is in another directory and gave its absolutepath so by using cat command on the absolutepath gives us the flag .

![a](https://github.com/user-attachments/assets/9235b846-ddcb-4940-a183-60d7f93c688a)





**more catting practice

The exercise here says that :
>You can specify all sorts of paths as arguments to commands, and we'll practice some more with cat. In this level, I'll put the flag in some crazy directory, and I will not allow you to change directories with cd, so no cat flag for you. You must retrieve the flag by absolute path, wherever it is.


* in this exercise when we open the VS-code workspace 
we can see a instruction diplayed in the terminal like this: 
![image](https://github.com/user-attachments/assets/04a689e9-4a56-4a84-9a7f-dd072f8f17dd)

*by looking at the instruction we can understand that the flag is in the directory that is specified in the instruction 
*so by using cat command to the absolutepath provided in the instruction will give us te flag.


![image](https://github.com/user-attachments/assets/fec0c374-9d21-4e55-9e67-2f6cdfc440e6)





**grepping for a needle in a haystack

in this exercise we are going to learn about the grep command 
>this takes us to the question where we actually use the grep command
>Sometimes, the files that you might cat out are too big. Luckily, we have the grep command to search for the contents we need!
>now the next question that arises is how to use it for that there is an example given in the exerise that is
>There are many ways to grep, and we'll learn on way here:

>![image](https://github.com/user-attachments/assets/35673684-a5fc-4c50-afa5-15e24783509a)
>Invoked like this, grep will search the file for lines of text containing SEARCH_STRING and print them to the console.


The exercise here says that :
>In this challenge, I've put a hundred thousand lines of text into the /challenge/data.txt file. Grep it for the flag!
>and it also gave us a hint
>HINT: The flag always starts with the text pwn.college.


* from the exercise we get to know that the flag is in the absolutepath /challenge/data.txt
* but it also specifies that the file which we cat contains alot of text and the fag is in it somewhere
* so we can understand that to find the flag we need to use grep command
* but now the question is that what argument should we provide to find the flag
* now we can make use of the hint where it says that the flag always starts with the text pwn.college.
* so now by using cat command on the  absolute path provided along with the grep command with the argument pwn.college gives us the flag

![image](https://github.com/user-attachments/assets/5748f190-74a8-40c3-b779-3a6113a25125)
*note the symbol '|'which we used in between the two commands is used to link two commands





**listing files 
in this exercise we are going to learn aout the ls command are :
The points that the exercise tells about ls command are
>So far, we've told you which files to interact with. But directories can have lots of files (and other directories) inside them, and we won't always be here to tell you their names. You'll need to learn to list their contents using the ls command!
>ls will list files in all the directories provided to it as arguments, and in the current directory if no arguments are provided. Observe:
>![image](https://github.com/user-attachments/assets/df135bae-261d-45ff-930a-63fccd8593ea)

The exercise here says that :
>In this challenge, we've named /challenge/run with some random name! List the files in /challenge to find it.

* here from the information given in the exercise it is said that  theyhave named the ?challenge?run with some random name
* we know that /challenge/run would give us the flag so they are saying that the name of the file which give us the flag has been renamed to some other name
* so to find it we have to ls command on /challenge directory
* when we do so we find two directories inside it
* those are:24555-renamed-run-29126 and  DESCRIPTION.md
* we can assume that the flag is in the 1st file as we can say that the 2nd file is a markdownfile whichcontains the desvription of the challenge
* so by writing the command /challenge/24555-renamed-run-29126 we can get the flag

![image](https://github.com/user-attachments/assets/c0ee3bab-0c10-437f-82eb-e5393858be09)





**touching files
in this exercise we are going to learn about the touch command 
The points that this exercise tells us about the touch command are :
>Of course, you can also create files! There are several ways to do this, but we'll look at a simple command here. You can create a new, blank file by touching it with the touch command:
>![image](https://github.com/user-attachments/assets/da8ecd90-e4cd-4949-a6c2-51067053721f)

The exercise here says that :
>It's that simple! In this level, please create two files: /tmp/pwn and /tmp/college, and run /challenge/run to get your flag!

* it is a simple exercise it says us to create two files in the tmp directory using touch command
* so first we use touch command to create a file /temp/pwn
* again we use the touch command to create a file /temp/challenge
* now we will execute the command /challenge/run in order to get the flag

![image](https://github.com/user-attachments/assets/4fa3331e-1ac9-421e-89a6-fc024b58d470)





**removing files
in this exercise we are going to learn about the rm command
The points that the exercise gives us about the rm command are:
>Files are all around you. Like candy wrappers, there'll eventually be too many of them. In this level, we'll learn to clean up!
>In Linux, you remove files with the rm command, as so:
>![image](https://github.com/user-attachments/assets/68f43e92-b287-49ee-aa83-836554be63f1)

The exercise here says that:
>Let's practice. This challenge will create a delete_me file in your home directory! Delete it, then run /challenge/check, which will make sure you've deleted it and then give you the flag!

* here in this exercise it is said that  a file name delete_me is in the home directory
*  so now the task is to delete this file from the directory
*  so now we need to write the command rm and the argument delete_me to delete it
* now check in the directory using ls command if the file is deleted or not
* after checking run the command /challenge/check to get the flag


![image](https://github.com/user-attachments/assets/d907e279-6006-4065-bd04-741751650a49)





**hidden files 
in this exercise we are going to learn about the (ls -a) command
The points about this command that are mentioned in this exercise are:
>Interestingly, ls doesn't list all the files by default. Linux has a convention where files that start with a . don't show up by default in ls and in a few other contexts. To view them with ls, you need to invoke ls with the -a flag, as so:
>![image](https://github.com/user-attachments/assets/0e8ecc49-2cad-4977-9bc2-10d88cbfef07)

The exercise here says that :
>Now, it's your turn! Go find the flag, hidden as a dot-prepended file in /.

* here in the exercise it is said that flag is hidden in a dot-prepended file
* which is in the directory /.
* so first use ls command on /.to see all the files except for the hidden ones
* now use ls -a command so as to see all the files even the hidden ones
* now we are able to see a dot prepended file .flag-1009111513213
* now run the command cat /.flag-1009111513213 to get the flag 


  ![image](https://github.com/user-attachments/assets/fd837d9e-d990-434b-8ac6-4e80646e39d7)
  * note- in linux dot-prepended files  refers to files/directories with a . prepended to their name.





    **an epic filesysstem quest
    this is not a regular exercise
    it is kind of quest

   The decription about this quest are:
    >With your knowledge of cd, ls, and cat, we're ready to play a little game!We'll start it out in /. Normally:
>![image](https://github.com/user-attachments/assets/399d7131-7f79-44ea-88cb-fe63fab6efcb)
>That's a lot of contents! One day, you will be quite familiar with them, but already, you might recognize the flag file and the challenge directory.


Now if we get into the quest the instructions given are:
>In this challenge, I have hidden the flag! Here, you will use ls and cat to follow my breadcrumbs and find it! Here's how it'll work:
>Your first clue is in /. Head on over there.
>Look around with ls. There'll be a file named HINT or CLUE or something along those lines!
>cat that file to read the clue!
>Depending on what the clue says, head on over to the next directory (or don't!).
>Follow the clues to the flag!

* First you have to enter the /.directory using cd command
* now you can see all the files using the command ls
* in these files you have a file called SNIPPET cat it
* now you get a clue which contains another directory to find another clue
* again go to the directory use ls to see all the files in it and then read the file which is in all bold letters to get another clue
* repeat this to find the flag
* in between this you will find a clue which says you can cd to the path where you need to ls the absolute directory to find the file with old letters in the directory
* after which you need to again use the whole absolute directory along with the file with bold letters to read it using cat command
  since you are not in the directory as you didnt use the cd command
* now again repeat the 4,5,6 steps till you get the flag and in the end you will find the flag in MESSAGE file

![image](https://github.com/user-attachments/assets/d93d85ef-6460-4489-86a3-c95e688bc31b)
![image](https://github.com/user-attachments/assets/b4f90d58-afd9-402b-9a4d-5d50408d9a1f)
![image](https://github.com/user-attachments/assets/70e3200e-13a7-4693-864a-13727f02b8b3)
![image](https://github.com/user-attachments/assets/a068c3fc-db67-4b1b-8501-acb896769f0f)





**making directories
in this exercise we will learn how to make directories
The points regarding this command mentioned in the exercise are:
>We can create files. How about directories? You make directories using the mkdir command. Then you can stick files in there!
>![image](https://github.com/user-attachments/assets/98a27d6e-44fd-4b85-8040-f8069d8a1d1b)

The exercie here says us to do:
>Now, go forth and create a /tmp/pwn directory and make a college file in it! Then run /challenge/run, which will check your solution and give you the flag!

* first according to the exercise we have to create a directory of /tmp/pwn
* we do it by using the command mkdir /tmp/pwn
* then we need to create a file college inside the directory
* we do it by using touch the whole directory along with the file name college like touch /tmp/pwn/college
* we can either do it by cding into the directory first and touch the file name then
* after that check the file by using ls command
* now run the command /challenge/run to get the flag

![image](https://github.com/user-attachments/assets/25f51744-256b-4aa7-88dc-55b6c84f34a7)





**finding files
in this exercise we will learn about the find command 
The points that are given about this command in this exercise are:
>The find command takes optional arguments describing the search criteria and the search location. If you don't specify a search criteria, find matches every file. If you don't specify a search location, find uses the current working directory (.). For example:
>![image](https://github.com/user-attachments/assets/15d1947f-33b6-4b15-b771-918a723d38bc)
>
>And when specifying the search location:
>![image](https://github.com/user-attachments/assets/6fb965be-7ea1-4e36-a392-a2c09be1a713)
>
>And, of course, we can specify the criteria! For example, here, we filter by name:
>![image](https://github.com/user-attachments/assets/0b84c7ab-0854-4867-a3b2-e07bd42777ba)
>
>You can search the whole filesystem if you want!
>![image](https://github.com/user-attachments/assets/b2f7bb58-357a-4445-929d-a90880327ade)

This exercise here says us to do :
>Now it's your turn. I've hidden the flag in a random directory on the filesystem. It's still called flag. Go find it!

>several notes. First, there are other files named flag on the filesystem. Don't panic if the first one you try doesn't have the actual flag in it. Second, there're plenty of places in the filesystem that are not accessible to a normal user. These will cause find to generate errors, but you can ignore those; we won't hide the flag there! Finally, find can take a while; be patient!

* here in the exercise it is said that  there is a flag file in the filesystem where the required flag is there
* but in order to get it we need to find the flag using the find command
* but there are multiple files with the name flag when you use the find command
* so we need to cat each and every directory which does not say permission denied
* then you will find the flag in one directory

  ![image](https://github.com/user-attachments/assets/d0efc4dd-05ee-470d-8a7b-79fdce55ddb9)
  ![image](https://github.com/user-attachments/assets/1e6981ad-c697-493b-86cb-6d8c63044194)





  ** linking files
  in this exercise we are going to learn about the ln command
  > The points about this command that are given in the given exercise are:
  > If you use Linux (or computers) for any reasonable length of time to do any real work, you will eventually run into some variant of the following situation: you want two programs to access the same data, but the programs expect that data to be in two different locations. Luckily, Linux provides a solution to this quandry: links.

Links come in two flavors: hard and soft (also known as symbolic) links. We'll differentiate the two with an analogy:

A hard link is when you address your appartment using multiple addresses that all lead directly to the same place (e.g., Apt 2 vs Unit 2).
A soft link is when you move appartments and have the postal service automatically forward your mail from your old place to your new place.
In a filesystem, a file is, conceptually, an address at which the contents of that file live. A hard link is an alternate address that indexes that data --- accesses to the hard link and accesses to the original file are completely identical, in that they immediate yield the necessary data. A soft/symbolic link, instead, contains the original file name. When you access the symbolic link, Linux will realize that it is a symbolic link, read the original file name, and then (typically) automatically access that file. In most cases, both situations result in accessing the original data, but the mechanisms are different.

Hard links sound simpler to most people (case in point, I explained it in one sentence above, versus two for soft links), but they have various downsides and implementation gotchas that make soft/symbolic links, by far, the more popular alternative.

In this challenge, we will learn about symbolic links (also also known as symlinks). Symbolic links are created with the ln command with the -s argument, like so:

![image](https://github.com/user-attachments/assets/8a7501e0-22c1-4e56-bd41-2bf336968beb)
> You can see that accessing the symlink results in getting the original file contents! Also, you can see the usage of ln -s. Note that the original file path comes before the link path in the command!

A symlink can be identified as such with a few methods. For example, the file command, which takes a filename and tells you what type of file it is, will recognize symlinks:
![image](https://github.com/user-attachments/assets/a2acc033-8a15-4c3e-8389-4e379a483df2)


This exercise wants us to do :
>Okay, now you try it! In this level the flag is, as always, in /flag, but /challenge/catflag will instead read out /home/hacker/not-the-flag. Use the symlink, and fool it into giving you the flag!

* here in this exercise first we have to link the /flag and /home/hacker/not-the-flag
* so then use ln -s command to link these two
* and then run /challenge/catflag command to get the flag

![image](https://github.com/user-attachments/assets/2fd878d5-713a-455f-9fe4-f80dc30b06ba)





































   














