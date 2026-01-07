What is an alias in Bash?

An alias is a nickname for a command.

Instead of typing a long or repetitive command every time, you can give it a short name. Bash then replaces that short name with the full command before running it.

Think of it as text substitution for commands.

Basic example

Instead of typing:

ls -la


You define an alias:

alias ll="ls -la"


Now when you type:

ll


Bash internally turns it into:

ls -la


You didn't create a new command — Bash just substituted text and ran the result.

aliases work only in interactive shells

Aliases:

✅ Work in your terminal (interactive shell)

❌ Do not work in scripts (.sh files)

Example:

# This works in terminal
alias ll="ls -la"

# This will NOT work inside a script
ll


Why?
Scripts are meant to be predictable and portable. Aliases are personal shortcuts, so Bash ignores them in scripts by default.


!!!!!!!!! IMPORTANT !!!!!!!

Replacement only happens in the first word!!

Aliases are expanded only for the command name, not arguments.

Works:
alias ll="ls -la"
ll /home

Does NOT work:
alias grep="grep --color=auto"
echo "test" | grep test   # works
echo "test" | \grep test  # bypasses alias

Cannot do logic or arguments

You cannot do this reliably with aliases:

alias mkcd="mkdir $1 && cd $1"   # Xbroken


Because aliases don't understand $1, variables, or logic.

Viewing and removing aliases
List all aliases
alias

View a specific alias
alias nmapp

Remove an alias
unalias nmapp

Making aliases permanent

Aliases you type in the terminal disappear when you close it.

To keep them:

Add them to ~/.bashrc (or ~/.zshrc for zsh)

Example:

nano ~/.bashrc


Add:

alias ll="ls -la"
alias gs="git status"


Then reload:

source ~/.bashrc