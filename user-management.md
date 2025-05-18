## Account Management
===================================================
| command | Description     |
| :-------- | :------- | 
| IMPORTANT FILES
| `/etc/passwd` | users and info: username:x:uid:gid:comment:home_directory:login_shell
| `/etc/shadow` | users' passwords
| `/etc/group ` | groups
|`useradd [OPTIONS] username`|creating a user account|
|OPTIONS:|
| `-m` | create home directory
| `-d` | directory => specify another home directory
| `-c` | "comment"
| `-s` | shell
| `-G` | specify the secondary groups (must exist)
| `-g` | specify the primary group (must exist)
|Exemple:|
| `useradd -m -d /home/john -c "C++ Developer" -s /bin/bash -G sudo,adm,mail john` |

## changing a user account
| command | Description  |
| :-------- | :------- | 
|`usermod [OPTIONS] username`| uses the same options as useradd
|Example:|
|`usermod -aG developers,managers john` | adding the user to two secondary groups
|`userdel -r username`| -r removes user's home directory as well
| `groupadd group_name` | creating a group
| `groupdel group_name` | deleting a group
| `cat /etc/groups` | displaying all groups
|`groups`|displaying the groups a user belongs to groups
## creating admin users
| command | Description     |
| :-------- | :------- | 
| `usermod -aG sudo john` | add the user to sudo group in Ubuntu and wheel group in CentOS

## Monitoring Users
| command | Description     |
| :-------- | :------- | 
|`who -H` | displays logged in users
|`id` | displays the current user and its groups
|`whoami` | displays EUID
|`w` and `uptime` |listing who’s logged in and what’s their current process.
|`last` and `last -u username`| printing information about the logins and logouts of the users