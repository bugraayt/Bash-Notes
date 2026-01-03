String refers to a sequence of characters which is treated as a single unit.

In Bash programming, almost everything is a string. When we type a command, the command's name is a string and each argument is a string; variable names are strings, and the contents of variables are strings as well; a filename is a string, and most files contain strings. They're everywhere!

An entire command can also be considered a string. This is not normally a useful point of view, but it illustrates the fact that parts of strings can sometimes be considered strings in their own right. A string which is part of a larger string is called a substring.

Strings do not have any intrinsic meaning. Their meaning is defined by how and where they are used. 

With the editor, write a shopping list and save it with the filename "list", and use cat to print it:

$ cat list
shampoo
tissues
milk (skim, not whole)

We typed a command: cat list. The shell reads this command as a string, and then divides it into the substrings cat and list. As far as the shell is concerned, list has no meaning, it's just a string with four characters in it. cat receives the argument list, which is a string of a filename. The string list has become meaningful because of how it was used. 

The file happens to contain some text, which we see on our terminal. The entire file content — taken as a whole — is a string, but that string is not meaningful. However, if we divide the file into lines (and therefore treat each line as a separate string), then we see each individual line has meaning.

We can divide the final line into words, but these words are not meaningful by themselves. We can't buy "(skim" at the store, and we might get the wrong kind of "milk". Dividing the lines into words is not a useful thing to do in this example. But the shell doesn't know any of this — only we do!

So, when we are dealing with commands, data, and variables — all of which are just strings to the shell — we have all the responsibility. We need to be sure everything that needs to be separated is separated properly, and everything that needs to stay together stays together properly. We'll touch on these concepts repeatedly as we continue. 
