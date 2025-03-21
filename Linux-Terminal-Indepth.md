## Linux Command Structure

### ping
===================================================
| command | example     | Description                |
| :-------- | :------- | :------------------------- |
| `ping` | `ping -c 1 8.8.8.8` | Check the connection between network connectivity to destination host

##### "ping" -> command
##### "-c" -> Option
##### 8.8.8.8 -> argument

## Getting Help,Man Pages (man,type,help.apropos)
===================================================
| command | example     | Description                |
| :-------- | :------- | :------------------------- |
| `man` | `man ls` | Use to read documentation of specific command 
| `type` | `type df,type cd` | Use to display path of command file for what type of file is this 
| `ifconfig` | `man -k ifconfig` | Use to display information about network interface
| `help` | `help cd, help alias` | Use only for shell built-in commands such as cd,alias etc. not for executable files

#### Notes
###### There are 2 types of files on linux 
###### executable such as df,rm,yum etc 
###### built-in such as cd,aliasa

## Keyboard Shortcuts
===================================================
| command | Description     |
| :-------- | :------- | 
| `TAB` | autocompletes the command or the filename if its unique
| `TAB TAB (press twice)` | displays all commands or filenames that start with those letters
| `CTRL + L` | clearing the terminal
| `CTRL + D` | closing the shell (exit)
| `CTRL + U` |  cutting (removing) the current line 
| `CTRL + A` |  moving the cursor to the start of the line
| `CTRL + E` |  moving the cursor to the end of the line
| `CTRL + C` |  stopping the current command
| `CTRL + Z` |  sleeping a the running program
| `CTRL + ALT + T` |  opening a terminal 

## Bash History
===================================================
| command | Description     |
| :-------- | :------- | 
| `history` | showing the history
| `history -d 100` | removing a line (ex: 100) from the history
| `history -c` | removing the entire history
| `echo $HISTFILESIZE` | printing the no. of commands saved in the history file (~/.bash_history)
| `echo $HISTSIZE` |  printing the no. of history commands saved in the memory
| `!!` |  rerunning the last command from the history
| `!20` |  running  a specific command from the history (ex: the 20th command)
| `!-10` |   running the last nth (10th) command from the history
| `!abc` |  running the last command starting with abc
| `!abc:p` |  printing the last command starting with abc
| `CTRL + R` |  reverse searching into the history 
| `HISTTIMEFORMAT="%d/%m/%y %T"` |  recording the date and time of each command in the history
| `echo "HISTTIMEFORMAT=\"%d/%m/%y %T\"" >> ~/.bashrc` |   making it persistent after reboot

## Running commands as root (sudo, su)
===================================================
| command | Description     |
| :-------- | :------- | 
| `sudo` | running a command as root (only users that belong to sudo group [Ubuntu] or wheel [CentOS])
| `sudo su` | becoming root temporarily in the terminal and enter the user's password
| `sudo passwd root` | setting the root password
| `passwd username` | changing a user's password
| `su` | becoming root temporarily in the terminal and enter the root passwords