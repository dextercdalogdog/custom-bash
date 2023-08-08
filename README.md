
# Custom Personal Bash



## Open your shell's configuration file (e.g., .bashrc) in a text editor:

```bash
  nano ~/.bashrc
```

## Add the following code at the end of the file:
```bash
# Function to get Git branch name
git_branch() {
    branch=$(git symbolic-ref --short HEAD 2>/dev/null)
    if [ $? -eq 0 ]; then
        echo "($branch)"
    fi
}

# Customize the PS1 (prompt) variable
PS1='\[\e[1;32m\]\u\[\e[m\]:\[\e[1;34m\]\W\[\e[m\] $(git_branch)\n\[\e[1;36m\]→ \[\e[m\]'

```
##### This code sets up the PS1 variable to display the current user in green, followed by a colon, the current directory name in blue, the Git branch (if available) in its own color and format, and finally a right arrow (→) symbol. The arrow is displayed in cyan.

## Save the changes and exit the text editor.
## To apply the changes, either restart your terminal or run the following command:
```bash
source ~/.bashrc
```