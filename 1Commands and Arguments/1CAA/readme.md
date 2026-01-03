Bash divides each line into words that are demarcated by a whitespace character (spaces and tabs). 
The first word of the line is the name of the command to be executed. All the remaining words become arguments to that command 
(options, filenames, etc.). 

Assume we're in an empty directory... (to try these commands, create an empty directory called test and enter that directory 
by running: mkdir test; cd test):

$ ls              # List files in the current directory (no output, no files).
$ touch a b c     # Create files 'a', 'b', and 'c'.
$ ls              # List files again, and this time outputs: 'a', 'b', and 'c'.
a  b  c

The command ls prints out the names of the files in the current directory. The first time we run the list command we get no output, because there are no files yet. 

The # character at the start of a word indicates a comment. Any words following the comment are ignored by the shell, meant only for reading. If we run these examples in our own shell, we don't have to type the comments; but even if we do, the command will still work. 

touch is an application that changes the Last Modified time of a file. If the filename that it is given does not exist yet, it creates a file of that name as a new and empty file. In this example, we passed three arguments. touch creates a file for each argument. ls shows us that three files have been created.

$ rm *            # Remove all files in the current directory.
$ ls              # List files in the current directory (no output, no files).
$ touch a   b c   # Create files 'a', 'b' and 'c'.
$ ls              # List files again; this time the outputs: 'a', 'b' and 'c'.
a  b  c

rm is an application that removes all the files that it was given. * is a glob. It basically means all and in this case means all files in the current directory.

Now, did we notice that there are several spaces between a and b, and only one between b and c? Also, notice that the files that were created by touch are no different than the first time. The amount of whitespace between arguments does not matter! This is important to know. For example: 

$ echo This is a test.
This is a test.
$ echo This    is    a    test.
This is a test.

echo is a command that prints its arguments to standard output (which in our case is the terminal). In this example, we provide the echo command with four arguments: 'This', 'is', 'a', and 'test.'. echo takes these arguments, and prints them out one by one with a space in between. In the second case, the exact same thing happens. The extra spaces make no difference. If we want the extra whitespace, we need to pass the sentence as one single argument. We can do this by using quotes: 

$ echo "This    is    a    test."
This    is    a    test.

Quotes group everything inside them into a single argument. The argument is: 'This    is    a    test.'... specifically spaced. The quotes are not part of the argument — Bash removes them before handing the argument to echo. echo prints this single argument out just like it always does.

Be very careful to avoid the following:

ls
This is a test.mp3      b
a                       c
rm This is a test.mp3.          #Executes rm with 4 arguments not 1
rm: This: No such file or directory
rm: is: No such file or directory
rm: test.mp3: No such file or directory
ls
This is a test.mp3      c
b                         
#Current directory is still here but the file 'a' is now gone!

!We need to make sure we quote filenames properly. If we don't, we'll end up deleting the wrong things! rm takes filenames as arguments. If filename have spaces use quotes!

This is what we should have done: 
$ rm "This is a test.mp3"

Arguments are separated from the command name and from each other by a whitespace. This is important to remember. For example, the following is wrong: 

$ [-f file]
bash: [-f: command not found

This is intended to test for the existence of a file named "file". It's reasonable to assume that whitespace around [ and ] doesn't matter, but [ is actually a command, and it requires its last argument to be ]. (We will cover the [ command in more detail later.) Therefore, we must separate [ from -f and ] from file, otherwise Bash will think we are trying to execute a command named [-f with a single argument file]. The correct command separates all arguments with whitespace:

$ [ -f file ]

And, if our filename contains whitespace or other special characters, it should also be quoted:

$ [ -f "my file" ]

Additionally:

    Tip — Always quote sentences or strings that belong together, even if it's not absolutely necessary. This developed practice will reduce the risk of human error in the scripts. (e.g. quoting a sentence of an echo command). 