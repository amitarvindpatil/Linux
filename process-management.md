## Process Viewing (ps, pstree, pgrep)
===================================================
| command | Description     |
| :-------- | :------- | 
| checking if a command is shell built-in or executable file
|`type rm` | rm is /usr/bin/rm
|`type cd` | cd is a shell built-in
## displaying all processes started in the current terminal
| command | Description     |
| :-------- | :------- | 
|`pstree`| displaying a hierarchical tree structure of all running processes
|`pstree -c`|prevent merging identical branches
|`ps -ef --forest`| ASCII art process tree
|`ps -f -u username`| displaying all processes of a specific user
|`pgrep -l sshd`| checking if a process called sshd is running
|`ps`| displaying all processes started in the current terminal
|`ps -ef` | displaying all processes running in the system
|`ps aux` |
`ps aux|less` | piping to less|
`ps aux --sort=%mem|less`| sorting by memory and piping to less|
`ps -ef|grep sshd`| 