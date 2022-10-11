
# 0x02-shell_redirections


Redirection is the ability to redirect the input and output of various commands to and from files or devices. We are going to see how redirecting works in Bash: the default shell in the majority of Linux distributions.

# ABOUT
# REQUIREMENTS
# HOW 
# PROJECT 


# ABOUT 

Shell redirections operators
In a shell, there are a few operators to perform redirections. Those are >, >>, <, <<, >&, <&.

>, >>, and <
Those 3 operators have one main thing in common: They interact with input/output files.

> and >> are used to redirect output from a program into a file.

$> cat my_file.txt > my_new_file.txt # The output from cat is redirect to a file caled my_new_file.txt
(If the file does not exist, it is created)

The difference between > and >> is that > truncates the file it is outputing to and >> appends to the output file.

$> echo Hello World! > greeting.txt # Creates a file with 'Hello World!' as the content

$> echo How are you? >> greeting.txt # Append 'How are you?' to greeting.txt
< allows you to use a file as input. So stdin becomes the file.

$> base64 < greeting.txt # base64 will use stdin as input which is redirected to greeting.txt by the shell
You can also combine multiple redirection operators:

$> cat < a.txt > b.txt # Reads from a.txt and outputs to b.txt
And <<
That one is a bit like the three above, except that it does not interact with files. Instead it is used to get input from the user's keyboard line by line.

Let stop here 

# HOW 

Shell, I/O Redirection
What do the commands head, tail, find, wc, sort, uniq, grep, tr do
How to redirect standard output to a file ?
How to get standard input from a file instead of the keyboard
How to send the output from one program to the input of another program ?
How to combine commands and filters with redirections?
Special Characters
What are special characters ?
Understand what do the white spaces, single quotes, double quotes, backslash, comment, pipe, command separator, tilde and how and when to use them
Other Man Pages
How to display a line of text ?
How to concatenate files and print on the standard output
How to reverse a string ?
How to remove sections from each line of files ?
What is the /etc/passwd file and what is its format ?
What is the /etc/shadow file and what is its format ?

# REQUIREMENTS  


Allowed editors: vi, vim, emacs
All your scripts will be tested on Ubuntu 20.04 LTS
All your scripts should be exactly two lines long ($ wc -l file should print 2)
All your files should end with a new line (why?)
The first line of all your files should be exactly #!/bin/bash
A README.md file, at the root of the folder of the project, describing what each script is doing
You are not allowed to use backticks, &&, || or ;
All your files must be executable
You are not allowed to use sed or awk

# PROJECT 

 [0-hello_world](https://github.com/Jadvdm/alx-system_engineering-devops/blob/master/0x02-shell_redirections/0-hello_world)
mandatory
Write a script that prints “Hello, World”, followed by a new line to the standard output.

[1-confused_smiley](https://github.com/Jadvdm/alx-system_engineering-devops/blob/master/0x02-shell_redirections/1-confused_smiley) Write a script that displays a confused smiley "(Ôo)'.

[2-hellofile](https://github.com/Jadvdm/alx-system_engineering-devops/blob/master/0x02-shell_redirections/2-hellofile)Display the content of the /etc/passwd file.

[3-twofiles](https://github.com/Jadvdm/alx-system_engineering-devops/blob/master/0x02-shell_redirections/3-twofiles) Display the content of /etc/passwd and /etc/hosts

[4-lastlines](https://github.com/Jadvdm/alx-system_engineering-devops/blob/master/0x02-shell_redirections/4-lastlines) Display the last 10 lines of /etc/passwd

[5-firstlines](https://github.com/Jadvdm/alx-system_engineering-devops/blob/master/0x02-shell_redirections/5-firstlines) Display the first 10 lines of /etc/passwd

[6-third_line](https://github.com/Jadvdm/alx-system_engineering-devops/blob/master/0x02-shell_redirections/6-third_line) Write a script that displays the third line of the file

[7-file](https://github.com/Jadvdm/alx-system_engineering-devops/blob/master/0x02-shell_redirections/7-file) Write a shell script that creates a file named exactly \*\\'"Best School"\'\\*$\?\*\*\*\*\*:) containing the text Best School ending by a new line.

[8-cwd_state](https://github.com/Jadvdm/alx-system_engineering-devops/blob/master/0x02-shell_redirections/8-cwd_state) Write a script that writes into the file ls_cwd_content the result of the command ls -la. If the file ls_cwd_content already exists, it should be overwritten. If the file ls_cwd_content does not exist, create it.

[9-duplicate_last_line](https://github.com/Jadvdm/alx-system_engineering-devops/blob/master/0x02-shell_redirections/9-duplicate_last_line) Write a script that duplicates the last line of the file iacta

The file iacta will be in the working directory

[10-no_more_js](https://github.com/Jadvdm/alx-system_engineering-devops/blob/master/0x02-shell_redirections/10-no_more_js) Write a script that deletes all the regular files (not the directories) with a .js extension that are present in the current directory and all its subfolders.

[11-directories](https://github.com/Jadvdm/alx-system_engineering-devops/blob/master/0x02-shell_redirections/11-directories) Write a script that counts the number of directories and sub-directories in the current directory.

The current and parent directories should not be taken into account
Hidden directories should be counted

[12-newest_files](https://github.com/Jadvdm/alx-system_engineering-devops/blob/master/0x02-shell_redirections/12-newest_files) Create a script that displays the 10 newest files in the current directory.

Requirements:

One file per line
Sorted from the newest to the oldest

[13-unique](https://github.com/Jadvdm/alx-system_engineering-devops/blob/master/0x02-shell_redirections/13-unique) Display lines containing the pattern “root” from the file /etc/passwd

[14-findthatword](https://github.com/Jadvdm/alx-system_engineering-devops/blob/master/0x02-shell_redirections/14-findthatword) Display the number of lines that contain the pattern “bin” in the file /etc/passwd

[15-countthatword](https://github.com/Jadvdm/alx-system_engineering-devops/blob/master/0x02-shell_redirections/15-countthatword) Display lines containing the pattern “root” and 3 lines after them in the file /etc/passwd.

[16-whatsnext](https://github.com/Jadvdm/alx-system_engineering-devops/blob/master/0x02-shell_redirections/16-whatsnext) Display all the lines in the file /etc/passwd that do not contain the pattern “bin”.

[17-hidethisword](https://github.com/Jadvdm/alx-system_engineering-devops/blob/master/0x02-shell_redirections/17-hidethisword) Display all lines of the file /etc/ssh/sshd_config starting with a letter.

include capital letters as well

[18-letteronly](https://github.com/Jadvdm/alx-system_engineering-devops/blob/master/0x02-shell_redirections/18-letteronly) Replace all characters A and c from input to Z and e respectively.


