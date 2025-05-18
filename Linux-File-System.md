## Linux Paths
===================================================
| command | Description     |
| :-------- | :------- | 
| `.` | the current working directory
| `..` | the parent directory
| `~` | the user's home directory
| `cd` | changing the current directory to user's home directory
| `cd ~` | changing the current directory to user's home directory
| `cd -` | changing the current directory to the last directory
| `cd /path_to_dir` | changing the current directory to path_to_dir 
| `pwd` | printing the current working directory
| `sudo apt install tree` | installing tree
| `tree directory/` | Ex: tree .
| `tree -d . ` | prints only directories
| `tree -f .` |  prints absolute paths

## ls command   
==================================================
| command | Description     |
| :-------- | :------- | 
| `ls` | listing the current directory
| `ls ~ /var /` | listing more directories
| `ls -la ~` | -a => listing all files and directories including hidden ones
| `ls -1 /etc` | -1 => listing on a single column
| `ls -ld /etc` | -d => displaying information about the directory, not about its contents
| `ls -h /etc` | -h => displaying the size in human readable format
| `ls -Sh /var/log` | -S => displaying sorting by size
| `du -sh ~` | Note: ls does not display the size of a directory and all its contents. Use du instead
| `ls -lX /etc` | -X => displaying sorting by extension
| `ls --hide=*.log /var/log` | --hide => hiding some files
| `ls -lR ~` | -R => displaying a directory recursively
| `ls -li /etc` | -i => displaying the inode number

## File Timestamps and Date
==================================================
| command | Description     |
| :-------- | :------- | 
| `ls -lu` | displaying atime
| `ls -lt` | displaying mtime
| `ls -lc` | displaying ctime
| `stat file.txt` | displaying all timestamps
| `ls -l --full-time /etc/` | displaying the full timestamp
| `touch file.txt` | creating an empty file if it does not exist, update the timestamps if the file exists
| `touch -a file` | changing only the access time to current time
| `touch -m file` | changing only the modification time to current time
| `touch -m -t 201812301530.45 a.txt` | changing the modification time to a specific date and time
| `touch -d "2010-10-31 15:45:30" a.txt` | changing both atime and mtime to a specific date and time
| `touch a.txt -r b.txt` | changing the timestamp of a.txt to those of b.txt
| `date` | displaying the date and time
| `cal` | showing this month's calendar
| `cal 2021` | showing the calendar of a specific year
| `cal 7 2021` | showing the calendar of a specific month and year
| `cal -3` | showing the calendar of previous, current and next month
| `date --set="2 OCT 2020 18:00:00"` | setting the date and time
| `ls -l` | displaying the modification time and sorting the output by name.

## Viewing files (cat, less, more, head, tail, watch)
==================================================
| command | Description     |
| :-------- | :------- | 
| `cat filename` | displaying the contents of a file
| `cat filename1 filename2` | displaying more files
| `cat -n filename` | displaying the line numbers
| `cat filename1 filename2 > filename3` | concatenating 2 files
| `less filename` | viewing a file using less
| less Shortcuts | 
| `"` | h         => getting help
| `"` | q         => quit
| `"` | enter     => show next line
| `"` | space     => show next screen
| `"` | /string   => search forward for a string
| `"` | ?string   => search backwards for a string
| `tail filename` | showing the last 10 lines of a file
| `tail -n 15 filename` | showing the last 15 lines of a file
| `tail -n +5 filename` | showing the last lines of a file starting with line no. 5
| `tail -f filename` | showing the last 10 lines of the file in real-time
| `head filename` | showing the first 10 lines of a file
| `head -n 15 filename` | showing the first 15 lines of a file
| `watch -n 3 ls -l` | running repeatedly a command with refresh of 3 seconds

## Working with files and directory (touch, mkdir, cp, mv, rm, shred)
==================================================
| command | Description     |
| :-------- | :------- | 
| `touch filename` |  creating a new file or updating the timestamps if the file already exists
| `mkdir dir1` | creating a new directory
| `mkdir -p mydir1/mydir2/mydir3` | creating a directory and its parents as well
| cp Commands | 
| `cp file1 file2` | creating a new directory
| `cp file1 dir1/file2` | copying file1 to dir1 as another name (file2)
| `cp -i file1 file2` | copying a file prompting the user if it overwrites the destination
| `cp -p file1 file2` | preserving the file permissions, group and ownership when copying
| `cp -v file1 file2` | being verbose 
| `cp -r dir1 dir2/` | recursively copying dir1 to dir2 in the current directory
| `cp -r file1 file2 dir1 dir2 destination_directory/` | copy more source files and directories to a destination directory
| The mv command | 
| `mv file1 file2` | renaming file1 to file2
| `mv file1 dir1/` | moving file1 to dir1 
| `mv -i file1 dir1/` | moving a file prompting the user if it overwrites the destination file
| `mv -n file1 dir1/` | preventing a existing file from being overwritten
| `mv -u file1 dir1/` | moving only if the source file is newer than the destination file or when the destination file is missing
| `mv file1 dir1/file2` | moving file1 to dir1 as file2
| `mv file1 file2 dir1/ dir2/ destination_directory/` | moving more source files and directories to a destination directory 
| The rm command | 
| `rm file1` | removing a file
| `rm -v file1` | being verbose when removing a file
| `rm -r dir1/` | removing a directory
| `rm -rf dir1/` | removing a directory without prompting
| `rm -ri fil1 dir1/` | removing a file and a directory prompting the user for confirmation
| `shred -vu -n 100 file1` | secure removal of a file (verbose with 100 rounds of overwriting)

## Piping and Command Redirection

### Piping Examples:
==================================================
| command | Description     |
| :-------- | :------- | 
| `ls -lSh /etc/ | head` |  see the first 10 files by size
| `ps -ef | grep sshd` | checking if sshd is running
| Command Redirection  |
|  output redirection  |    
| `ps aux > running_processes.txt` |
| `who -H > loggedin_users.txt`    |
| appending to a file  |
| `id >> loggedin_users.txt` |
| output and error redirection |
| `tail -n 10 /var/log/*.log > output.txt 2> errors.txt`|
| redirecting both the output and errors to the same file |
| `tail -n 2 /etc/passwd /etc/shadow > output_errors.txt 2>&1` |
| `cat -n /var/log/auth.log | grep -ai "authentication failure" | wc -l` |
| `cat -n /var/log/auth.log | grep -ai "authentication failure" > auth.txt` | piping and redirection


## Finding Files (find, plocate)
| command | Description     |
| :-------- | :------- | 
|  LOCATE | locate is a symlink (shortcut) to plocate
| `sudo updatedb` | updating the plocate db
| finding file by name  |
|  `locate filename`  | filename is expanded to *filename*
|  `locate -i filename` | the filename is case insensitive
| `locate -r '/filename$'`| finding by exact name
| `locate -b filename` | finding using the basename 
| `locate -r 'regex'` | finding using regular expressions
| `locate -e filename` | checking that the file exists
| `which command` or `which -a command` | showing command path
| FIND | find path option
| `find ~ -type f -size +1M` | finding all files in ~ bigger than 1 MB
| Options: |
| `-type f, d, l, s, p`|
| `-name filename`|
|`-iname filename`| case-insensitive
|`-size n, +n, -n`|
|`-perm permissions`|
|`-links n, +n, -n`|
|`-atime n, -mtime n, ctime n`|
|`-group group_owner`|

## Searching for text patterns (grep)
| command | Description     |
| :-------- | :------- | 
|   `grep [OPTIONS] pattern file`|
|Options: |
|`-n`    | => print line number
|`-i`    | => case insensitive
|`-v`    | inverse the match
|`-w`    | search for whole words
|`-a`    | search in binary files
|`-R`    | search in directory recursively
|`-c`    | display only the no. of matches
|`-C n`  |#display a context (n lines before and after the match)

## VIM
### Modes of operation: Command, Insert, and Last Line Modes.
#### VIM Config File: ~/.vimrc
| command | Description     |
| :-------- | :------- | 
|# Entering the Insert Mode from the Command Mode|
|`i` | insert before the cursor
|`I` | insert at the beginning of the line
|`a` | insert after the cursor
|`A` | insert at the end of the line
|`o` | insert on the next line
|# Entering the Last Line Mode from the Command Mode|
|`:`|
|Returning to Command Mode from Insert or Last Line Mode |
| `ESC` |
|Shortcuts in Last Line Mode|
| `w!` | write/save the file
| `q!` | quit the file without saving
| `wq!`| save/write and quit
| `e!` | undo to the last saved version of the file
| `set nu` | set line numbers
| `set nonu` | unset line numbers
| `syntax on|off`|
| `%s/search_string/replace_string/g`|
| Shortcuts in Command Mode |
|`x  ` | remove char under the cursor
|`dd ` | cut the current line
|`5dd` | cut 5 lines
|`ZZ ` | save and quit
|`u  ` | undo
|`G  ` | move to the end of file
|`$  ` | move to the end of line
| `0 or ^`  | move to the beginning of file
| `:n (Ex :10)` | move to line n
| `Shift+v`     | select the current line
| `y`           | yank/copy to clipboard
| `p`          | paste after the cursor
| `P`           | paste before the cursor
| `/string`     | search for string forward
| `?string`    | search for string backward
| `n`           | next occurrence
| `N`           | previous occurrence
|`vim -o file1 file2`|Opening more files in stacked windows
|`vim -d file1 file2` |Opening more files and highlighting the differences
|`Ctrl+w` |move between files