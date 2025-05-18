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

### piping to less
`ps aux|less`

### sorting by memory and piping to less
`ps aux --sort=%mem|less`

`ps -ef|grep sshd`

## Dynamic Real-Time View of Processes(top)
===================================================
| command | Description     |
| :-------- | :------- | 
|`top`|starting top
|top shortcuts while it's running
|`h    ` | getting help
|`space` | manual refresh
|`d    ` | setting the refresh delay in seconds
|`q    ` | quitting top
|`u    ` | display processes of a user
|`m    ` | changing the display for the memory
|`1    ` | individual statistics for each CPU
|`x/y  ` | highlighting the running process and the sorting column
|`b    ` | toggle between bold and text highlighting
|`<    ` | move the sorting column to the left
|`>    ` | move the sorting column to the right
|`F    ` | entering the Field Management screen 
|`W    ` | saving top settings
|`top -d 1 -n 3 -b > top_processes.txt` |running top in batch mode (3 refreshes, 1 second delay)
|Interactive process viewer (top alternative)|
|`sudo apt update && sudo apt install htop `| Installing htop
|`htop`|

## Killing processes (kill, pkill, killall)
===================================================
| command | Description     |
| :-------- | :------- | 
|`kill -l`|listing all signals
|`kill pid` `# => Ex: kill 12547`| sending a signal (default SIGTERM - 15) to a process by pid 
|`kill -SIGNAL pid1 pid2 pid3 ...`| sending a signal to more processes
|sending a specific signal (SIGHUP - 1) to a process by pid|
|`kill -1 pid`|
|`kill -HUP pid`|
|`kill -SIGHUP pid`|
|sending a signal (default SIGTERM - 15) to process by process name|
|`pkill process_name`|          # => Ex: pkill sleep
|`killall process_name`|
|`kill $(pidof process_name)`|  # => Ex: kill -HUP $(pidof sshd)
## running a process in the background|
| command | Description     |
| :-------- | :------- | 
|`command &`|   # => Ex: sleep 100 &
|`jobs`| Showing running jobs
|`Ctrl + Z`| Stopping (pausing) the running process
|`fg %job_id`|resuming and bringing to the foreground a process by job_d
|`bg %job_id`|resuming in the background a process by job_d
|`nohup command &     # => Ex: nohup wget http://site.com &`| starting a process immune to SIGHUP
