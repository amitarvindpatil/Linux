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
| command | example     |
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

