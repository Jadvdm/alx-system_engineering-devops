# 0x03-shell_variables_expansions

Parameter expansion also known as variable expansion is the replacement of syntactic structures of the form $parameter and ${parameter} with the value of the parameter, possibly processed by the application of modifiers.

When a shell reads a command line it processes it through several well defined steps, such as splitting the line into words, performing several kinds of expansions (of which parameter expansion is but one), and applying any redirections. For example the Bash shell will first split the line into words. then it will perform brace expansion, tilde expansion, parameter and variable expansion, arithmetic expansion, command substitution and process expansion in left-to-right order, followed by final word splitting and pathname expansion.

I don't understand what you mean by "variable printing".

Globbing, or "pathname expansion" as the Bash documentation prefers to call it, happens after variable expansion; the shell examines each word on the command line for the presence of the characters *, ? and [, and, if any of them is found, considers the word to be a pattern and replaces it with the list of matching files, subject to certain configuration options.

# About 
# Requirements 
# project 


# About 

Brace expansion is the process of expanding every word containing a brace expression, of the form {w1,w2,w2}, where each w1 , w2 , w3 are words (without any space), into a sequence of words where the brace expression is replaced by w1 , w2 , w3 , respectively. For example, abc{de,fg,hi} expands into the sequence of words abcde abcfg abchi.
 1

Tilde expansion expands every ∼ into the path to your home directory. The form ∼name expands into the path to the home directory of user name .
Variable substitution and parameter expansion substitute the value of variables. Variable substitu- tion replaces every expression $var by the value of variable var . Parameter expansion is a kind of conditional substitution. There are many variations of parameter expansion. The most common one is to replace every expression of the form ${var :-word } either by the value of variable var if var is set and non-null, or by word if var does not exist, or is null-valued.
Command substitution replaces every expression of the form $(cmd ), where cmd is a command, by the output of the execution of cmd . Hence, $(pwd) is replaced by the output of pwd, that is, the current working directory.
Arithmetic substitution allows you to perform numerical computations in the shell, instead of using a program such as bc. An example of an arithmetic substitution is $(( 3 + 4 )), which gets replaced by 7. We will return to arithmetic expressions in later lectures.
Word splitting is the process of actually splitting the command line into tokens, at the spaces. Hence, if a substitution occuring earlier in the process substitutes a string with spaces, for example, $FOO where variable FOO has value some word, then that value will be split into two tokens at this step.
Finally, pathname expansion is the process of replacing paths containing wildcard characters (such as * and ?) by the sequence of paths that match the pattern. Recall that * matches one of more character, ? matches exactly one character, [abc] matches any character between the brackets (here, a, b, c), and [!abc] matches any character not in the brackets. (This process is also known as globbing.) Each filename in an expansion is taken as a token. Note that this step happens after word splitting, so that if there are spaces in filenames, each filename is still considered a token.
Sometimes, we want to disable some aspects of this automatic expansion by the shell. By and large, this process is known as quoting. Quoting can take many forms. The simplest form is simply to escape the special characters that have meaning to the shell. For instance, you may want to use the $ character without having it interpreted as variable, parameter or command substitution. Similarly for the &, ;, ?, *, [, ], {, } characters. To use such a special character as a literal character, you precede it with a backslash. (This is called escaping a character.) Since a backslash is itself a special character, if you want a literal backslash, you need to escape it as well.
Two alternate forms of quoting exist. The form ’text’ disables any form of expansion between the single quotes, including word splitting. Hence, a line cmd ’word1 word2’ will split the line into cmd and word1 word2, where the latter is a single token. The form "text" disables expansion between the double quotes, except for variable and command substitution. But again, word split- ting does not happen between the double quotes. Hence, "*$foo" will expand to *bar if variable foo has value bar. The quotes (single or double) are removed from the token when word splitting happens, and so never appear to what eventually gets invoked.

# Requirements 

Allowed editors: vi, vim, emacs

All your scripts will be tested on Ubuntu 20.04 LTS

All your scripts should be exactly two lines long ($ wc -l file should print 2)

All your files should end with a new line (why?)

The first line of all your files should be exactly #!/bin/bash

A README.md file, at the root of the folder of the project, describing what each script is doing

You are not allowed to use &&, || or ;

You are not allowed to use bc, sed or awk

All your files must be executable

# Project 

[]() Create a script that creates an alias.

Name: ls

Value: rm *

[0-alias](https://github.com/Jadvdm/alx-system_engineering-devops/blob/master/0x03-shell_variables_expansions/0-alias) Create a script that prints hello user, where user is the current Linux user.

[1-hello_you](https://github.com/Jadvdm/alx-system_engineering-devops/blob/master/0x03-shell_variables_expansions/1-hello_you) Add /action to the PATH. /action should be the last directory the shell looks into when looking for a program.

[2-path](https://github.com/Jadvdm/alx-system_engineering-devops/blob/master/0x03-shell_variables_expansions/2-path) Add /action to the PATH. /action should be the last directory the shell looks into when looking for a program.

