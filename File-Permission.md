## File Permissions
===================================================
| command | Description     |
| :-------- | :------- | 
| LEGEND
| u = User
| g = Group
| o = Others/World
| a = all
|r = Read
|w = write
|x = execute
|- = no access
|displaying the permissions (ls and stat)|
|`ls -l /etc/passwd`| output - -rw-r--r-- 1 root root 2871 aug 22 14:43 /etc/passwd 
|`stat /etc/shadow`|  
|changing the permissions using the relative (symbolic) mode
|chmod u+r filename
|chmod u+r,g-wx,o-rwx filename
|chmod ug+rwx,o-wx filename
|chmod ugo+x filename
|chmod a+r,a-wx filename
|changing the permissions using the absolute (octal) mod|
| PERMISSIONS   |   EXAMPLE
| u   g   o     |
| rwx rwx rwx   |  chmod 777 filename
| rwx rwx r-x   |  chmod 775 filename
| rwx r-x r-x   |  chmod 755 filename
| rwx r-x ---   |  chmod 750 filename
| rw- rw- r--   |  chmod 664 filename
| rw- r-- r--   |  chmod 644 filename
| rw- r-- ---   |  chmod 640 filename
|`chmod --reference=file1 file2`| setting the permissions as of a reference file
|`chmod -R u+rw,o-rwx filename`| changing permissions recursively
|SUID (Set User ID)|
|displaying the SUID permission|
|`ls -l /usr/bin/umount`| -rwsr-xr-x 1 root root 39144 apr  2 18:29 /usr/bin/umount
|`stat /usr/bin/umount` | 
|setting SUID|
|`chmod u+s executable_file`|
|`chmod 4XXX executable_file`|Ex: chmod 4755 script.sh
| SGID (Set Group ID)| 
| displaying the SGID permission|
| `ls -ld projects/` | drwxr-s--- 2 student student 4096 aug 25 11:02 projects/
| `stat projects/` |
| setting SGID|
|`chmod 2750 projects/`|
|`chmod g+s projects/`|
|The Sticky Bit |
|displaying the sticky bit permission|
|`ls -ld /tmp/`| drwxrwxrwt 20 root root 4096 aug 25 10:49 /tmp/
|`stat /tmp/`|  
|setting the sticky bit|
| mkdir temp |
| chmod 1777 temp/|
| chmod o+t temp/ |
| ls -ld temp/    | drwxrwxrwt 2 student student 4096 aug 25 11:04 temp/
|UMASK|
|`umask `| displaying the UMASK
|`umask new_value` `Ex: umask 0022` | setting a new umask value
| Changing File Ownership (root only)|
|`chown new_owner file/directory` `Ex: sudo chown john a.txt` | changing the owner
|`chgrp new_group file/directory`| changing the group owner
|`chown new_owner:new_group file/directory`| changing both the owner and the group owner
|`chown -R new-owner file/directory`| changing recursively the owner or the group owner
|`lsattr filename`| displaying the file attributes
|`chattr +-attribute filename'     '=> Ex: sudo chattr +i report.txt`|changing the file attributes
