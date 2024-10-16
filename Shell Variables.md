 **printing variables**  
 in this exercise we are going to learn how to print the variables
 Description given is:
> Let's start with printing variables out. The /challenge/run program will not, and cannot, give you the flag, but that's okay, because the flag has been put into the variable called "FLAG"! Just have your shell print it out!

>You can accomplish this using a number of ways, but we'll start with echo. This command just prints stuff. For example:
>![image](https://github.com/user-attachments/assets/fc1fd312-b48b-4794-890e-4968d86a907b)
>

>You can also print out variables with echo, by prepending the variable name with a $. For example, there is a variable, PWD, that always holds the current working directory of the current shell. You print it out as so:
>![image](https://github.com/user-attachments/assets/e417158d-bc79-4632-a1a9-3b490a92d0f4)

The exercise is :
>Now it's your turn. Have your shell print out the FLAG variable and solve this challenge!

* now we have to use the command echo $FLAG
* this command will help us to print the contents of the variable FLAG

![image](https://github.com/user-attachments/assets/0a6293bc-87d6-4386-9f9f-5bb2c1a08c99)





**SETTING_VARIABLES**

in this exercise we are going to learn how to assign values to a variable:
Keypoints on this exercise are:
>Naturally, as well as reading values stored in variables, you can write values to variables. This is done, as with many other languages, using =. To set variable VAR to value 1337, you would use:
>![image](https://github.com/user-attachments/assets/911b55cb-fe9c-47f1-b298-d239eda43a14)
>
>Note that there are no spaces around the =! If you put spaces (e.g., VAR = 1337), the shell won't recognize a variable assignment and will, instead, try to run the VAR command (which does not exist).

>Also note that this uses VAR and not $VAR: the $ is only prepended to access variables. In shell terms, this prepending of $ triggers what is called variable expansion, and is, surprisingly, the source of many potential vulnerabilities (if you're interested in that, check out the Art of the Shell dojo when you get comfortable with the command line!).

>After setting variables, you can access them using the techniques you've learned previously, such as:
>![image](https://github.com/user-attachments/assets/2ef0cdd9-1099-46ea-b2dc-8a50374db0cb)


The exercise is:
>To solve this level, you must set the PWN variable to the value COLLEGE. Be careful: both the names and values of variables are case-sensitive! PWN is not the same as pwn and COLLEGE is not the same as College.

* here we have to create a vsriable name and assign it to the ctring COLLEGE
* for this we write the command PWN=COLLEGE
* where we have assigned the value COLLEGE to the variable PWN
* we should not keep any spaces in this commmand anywher or else the terminal thinks of the word before space as a comman and try to run it

![image](https://github.com/user-attachments/assets/9644f4d2-b0cc-419e-ab4f-cab4b7f344fe)





**MULTI_WORD_VARIABLES**

in this exercise we are going to learn about how to assign multiword to a variable
The keypoint is:
> we need to write the words with the space between the double quotes""
> as space between words normally doesnt work as the terminal think it as of command and argments

The exercise is:
>Here, the shell reads 1337 SAUCE as a single token, and happily sets that value to VAR. In this level, you'll need to set the variable PWN to COLLEGE YEAH. Good luck!

* we have to write the value in double quotes
* like this PWN="COLLEGE YEAH"

![image](https://github.com/user-attachments/assets/e4800c4e-e848-4a67-8a21-024e361936c4)





**EXPORTING_VARIABLES**  

in this exercsie we are going to learn how to export variables
Keypoints are:
>By default, variables that you set in a shell session are local to that shell process. That is, other commands you run won't inherit them. You can experiment with this by simply invoking another shell process in your own shell, like so:
>![image](https://github.com/user-attachments/assets/c3edf948-0135-49be-a2d9-937af94e05c9)
>
>In the output above, the $ prompt is the prompt of sh, a minimal shell implementation that invoked as a child of the main shell process. And it does not receive the VAR variable!
>This makes sense, of course. Your shell variables might have sensitive or weird data, and you don't want it leaking to other programs you run unless it explicitly should. How do you mark that it should? You export your variables. When you export your variables, they are passed into the environment variables of child processes. You'll encounter the concept of environment variables in other challenges, but you'll observe their effects here. Here is an example:
>![image](https://github.com/user-attachments/assets/358637fc-2dd2-41fc-8f0e-6418f046e73f)
>
>Here, the child shell received the value of VAR and was able to print it out! You can also combine those first two lines.
>![image](https://github.com/user-attachments/assets/7ffeafad-ca19-4adb-821b-2011a8560014)


The exercise is:
>In this challenge, you must invoke /challenge/run with the PWN variable exported and set to the value COLLEGE, and the COLLEGE variable set to the value PWN but not exported (e.g., not inherited by /challenge/run). Good luck!

* first we have to create a variable PWN and assign it COLLEGE
* now we have to create the variable  COLLEGE and assign it PWN
* now export PWN but not COLLEGE using command export and argument PWN
* now run /challenge/run command with argument PWN to get the flag like this /challenge/run PWN

![image](https://github.com/user-attachments/assets/8036b2bd-14ed-4f3c-bab1-fe53a9557b1c)





**PRINTING EXPORTED_VARIABLES** 

in this exercise we are going to learn how to access variables without using echo 
>inthis exercise we are going to learn using env command

The exercise is:
>Try the env command: it'll print out every exported variable set in your shell, and you can look through that output to find the FLAG variable!

* here we use the command env to get the flag
* we use grep command to find the flag in the output of the env command
* so the command is env | grep pwn.college
* now we get the flag

![image](https://github.com/user-attachments/assets/56046c32-1a83-4065-b100-eb599c1f2ad7)





**STORING COMMAND_OUTPUTS**

in this exercise we ware foing to learn how to store command outputs into variables:
Keypoints are:
>In the course of working with the shell, you will often want to store the output of some command into a variable. Luckily, the shell makes this quite easy using something called Command Substitution! Observe:
>![image](https://github.com/user-attachments/assets/5f8eb00e-8a8f-4528-bf14-b982c06ce35c)
>
>Trivia: You can also backticks instead of $(): FLAG=`cat /flag` instead of FLAG=$(cat /flag) in the example above. This is an older format, and has some disadvantages (for example, imagine if you wanted to nest command substitutions. How would you do $(cat $(find / -name flag)) with backticks? The official stance of pwn.college is that you should use $(blah) instead of `blah`.

The xercise is:
>Neat! Now, you practice. Read the output of the /challenge/run command directly into a variable called PWN, and it will contain the flag!

* now first we have to store the output from the /challenge/run into the variable PWN
* by using the command PWN=$(/challenge/run)
* now echo the variable to get the flag like this echo $PWN

![image](https://github.com/user-attachments/assets/b36396c9-1e21-4a19-9f11-05c536a9dc79)





**READING_INPUT

in this exercise we wre going to learn how to read input
The keypoints are:
>We'll start with reading input from the user (you). That's done using the aptly named read builtin, which reads input!

Here is an example using the -p argument, which lets you specify a prompt (otherwise, it would be hard for you, reading this now, to separate input from output in the example below):
>
>![image](https://github.com/user-attachments/assets/f41b60ac-03c5-426d-bd94-ec273540845a)
>
>Keep in mind, read reads data from your standard input! The first Hello!, above, was inputted rather than outputted. Let's try to be more explicit with that. Here, we annotated the beginning of each line with whether the line represents INPUT from the user or OUTPUT to the user:
>![image](https://github.com/user-attachments/assets/0abce753-4b89-4de3-b21b-d2b74b93501a)

The exercsie is:
>In this challenge, your job is to use read to set the PWN variable to the value COLLEGE. Good luck!

* we have to write the command read -p "input:" PWN
* now write input COLLEGE
* so that youwill get the flag
  

![image](https://github.com/user-attachments/assets/1a06207a-a8a5-4347-851e-135f27c596b4)





**READING_FILES**

in this we are going to learn how to read files
Keypoints are:
>Often, when shell users want to read a file into an environment variable, they do something like:
>![image](https://github.com/user-attachments/assets/16f4b1ff-c469-4cd3-9796-5f97560beab0)
>
>This works, but it represents what grouchy hackers call a "Useless Use of Cat". That is, running a whole other program just to read the file is a waste. It turns out that you can just use the powers of the shell!
>previously, you read user input into a variable. You've also previously redirected files into command input! Put them together, and you can read files with the shell.
>![image](https://github.com/user-attachments/assets/f2453dba-c2b7-4f0a-a604-2fb7253eb4ba)

The exercise is:
> Now, use that to read /challenge/read_me into the PWN environment variable, and we'll give you the flag! The /challenge/read_me will keep changing, so you'll need to read it right into the PWN variable with one command!

* for this we have to use the command read PWN > /challenge/run


![image](https://github.com/user-attachments/assets/0defbabf-98d9-4782-89ca-83c54292047d)




















