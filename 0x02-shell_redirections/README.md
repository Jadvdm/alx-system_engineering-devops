
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

So when you do something like:

$> cat <<EOF
... and press enter, the shell will expect input.
So you can continue:

$> cat <<EOF
> Hello World!
> How are you?
> Do you know the answer to the ultimate question?
And when you want to stop the input you either press Ctrl+D or type the word which is on the right side of the << operator (In this case EOF) and press enter (it must be on an empty line):

$> cat << EOF
> Hello World!
> How are you?
> Do you know the answer to the ultimate question?
> EOF
Hello World!
How are you?
Do you know the answer to the ultimate question?
Immediatly after the input has been stoppedt the shell runs the program with what you have typed as the content in stdin.

>& and <&
Those two do not act on files but file descriptors.

Their left side can be either ignored or be a number (the target fd).
The left side MUST be attached to the operator.

If I want to redirect stdout to stderr I can do:

$> cat ft_strdup.c 1>&2
Or...

$> cat ft_strdup.c >&2
You can also use >& and <& to close a file descriptor (If you want to ignore error messages, for example)

$> find / -name 'lost_file' 2>&- # If you don't want to see messages like 'Permision denied'
The only difference between >& and <& is the default file descriptor used in case of a not given left fd.
>& is for stdout and <& is for stdin.

Also, if you put a space between the left side of the operator and the operator itself the shell will think that the left side is actually an argument to pass to the program and will use the default left side fd number.

One last thing
Those operators can be used anywhere on the command line

$> < input_file cat

$> >output_file echo hello world

$> ls 2>&- -R /
But you should put the them either on the beginning of the command or the ending to avoid confusion.

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
