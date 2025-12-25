BASH

BASH is an acronym for Bourne Again Shell. It is based on the Bourne shell and is mostly compatible with its features. 

Think of a shell as a way for you to speak to your system. Your system doesn't need it for most of its work, but it is an excellent 
interface between you and what your system can offer. It allows you to perform basic math, run basic tests and execute applications. 
More importantly, it allows you to combine these operations and connect applications to each other to perform complex and automated tasks. 

BASH is not your operating system. It is not your window manager. It is not your terminal (but it oftens runs inside your terminal). 
It does not control your mouse or keyboard. It does not configure your system, activate your screensaver, or open your files when you 
double-click them. It is generally not involved in launching applications from your window manager or desktop environment. 
It's important to understand that BASH is only an interface for you to execute statements (using BASH syntax), either at the interactive BASH prompt or via BASH scripts. 

You should make yourself familiar with the man and apropos commands on the shell. They will be vital to your self-tutoring.

$ man man
$ man apropos

Traditionally, a shell prompt either ends with $, % or #. If it ends with $, this indicates a shell that's compatible with the Bourne shell 
(such as a POSIX shell, or a Korn shell, or Bash). If it ends with %, this indicates a C shell (csh or tcsh); this guide does not cover C shell. 
If it ends with #, this indicates that the shell is running as the system's superuser account (root), and that you should be extra careful. 

Bash also offers a help command which contains brief summaries of its built-in commands (which we'll discuss in depth later on).

$ help
$ help read
