## Bash Alias
===================================================
| command | Description     |
| :-------- | :------- | 
| `listing all Aliases` | showing info about the boot process
| `alias copy="cp -i"` | creating an alias:  alias_name="command"
|to make the aliases you define persistent, add them to ~/.bashrc|
|`unalias copy`| removing an alias: unalias alias_name
|Useful Aliases| 
|`alias c="clear"`| 
|`alias cl="clear;ls;pwd"`| 
|`alias root="sudo su"`| 
|`alias ports="netstat -tupan"`| 
|`alias sshconfig="sudo vim /etc/ssh/sshd_config"`| 
|`alias my_server="ssh -p 3245-l user100 80.0.0.1"`| 
|`alias update=”sudo apt update && sudo apt dist-upgrade -y && sudo apt clean”`|
|`alias lt="ls -hSF --size -1"`|
|`alias ping='ping -c 5'`|    
|Interactive File Manipulation|
|`alias cp="cp -i"`|
|`alias mv="mv -i"`|
|`alias rm="rm -i"`|

## Important alias ##
# This may look a bit confusing, but essentially, 
# it makes all of the other aliases you define function correctly when used with sudo 
`alias sudo='sudo '`  | use single quotes, not double quotes.
