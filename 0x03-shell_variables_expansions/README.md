# 0x03-shell_variables_expansions

Parameter expansion also known as variable expansion is the replacement of syntactic structures of the form $parameter and ${parameter} with the value of the parameter, possibly processed by the application of modifiers.

When a shell reads a command line it processes it through several well defined steps, such as splitting the line into words, performing several kinds of expansions (of which parameter expansion is but one), and applying any redirections. For example the Bash shell will first split the line into words. then it will perform brace expansion, tilde expansion, parameter and variable expansion, arithmetic expansion, command substitution and process expansion in left-to-right order, followed by final word splitting and pathname expansion.

I don't understand what you mean by "variable printing".

Globbing, or "pathname expansion" as the Bash documentation prefers to call it, happens after variable expansion; the shell examines each word on the command line for the presence of the characters *, ? and [, and, if any of them is found, considers the word to be a pattern and replaces it with the list of matching files, subject to certain configuration options.

# About 
# Requirements 
# project 

