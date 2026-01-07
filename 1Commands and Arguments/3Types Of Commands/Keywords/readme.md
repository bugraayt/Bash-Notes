Keywords are like builtins, with the main difference being that keywords are 
actually Bash syntax and may be parsed using special rules. For example, 
[ is a Bash builtin, while [[ is a Bash keyword; they are both used to test 
for a variety of conditions. Here we try to use them to compare the words "a" 
and "b" lexicographically:

