
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

0. [Hello World](https://github.com/Jadvdm/alx-system_engineering-devops/blob/master/0x02-shell_redirections/0-hello_world)
mandatory
Write a script that prints “Hello, World”, followed by a new line to the standard output.

[1-confused_smiley](https://github.com/Jadvdm/alx-system_engineering-devops/blob/master/0x02-shell_redirections/1-confused_smiley) Write a script that displays a confused smiley "(Ôo)'.
