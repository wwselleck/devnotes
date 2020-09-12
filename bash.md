# Bash
## Syntax
### <()
- 💭 [What exactly is <() in bash (and =() in zsh)?](https://superuser.com/questions/1059781/what-exactly-is-in-bash-and-in-zsh)

<([command]) redirects output of command when pipe| isn't possible
Multiple commands, program doesn't take STDIN
Uses file in /dev/fd to hold output. Use `echo <(command)` to see this
diff <(ls dirA) <(ls dirB)
**set -e**
Exit immediately if a command fails
Printing trace of script
