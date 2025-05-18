## Software Management (dpkg and apt)
==================================================================
| command | Description     |
| :-------- | :------- | 
|### DPKG ###|
|`dpkg --info google-chrome-stable_current_amd64.deb`|  getting info about a deb file
|`sudo dpkg -i google-chrome-stable_current_amd64.deb`| installing an application from a deb file
|list all installed programs|
|`dpkg --get-selections`| 
|`dpkg-query -l`|
|finding to which package a file belongs |
|`which ls`|
|`dpkg -S /bin/ls`| coreutils: /bin/cp
|`sudo dpkg -r google-chrome-stable`|removing a package
|`sudo dpkg -P google-chrome-stable`|purging a package
##### filtering the output
`dpkg-query -l | grep ssh`
##### Listing all files of an installed package
`dpkg-query -l | grep ssh`

`dpkg -L openssh-server`

### APT ###
===============================================
| command | Description     |
| :-------- | :------- | 
|`sudo apt update`|updating the package index (doesn't install/uninstall/update any package)
|`sudo apt install apache2`|  installing or updating a package named apache2
|`sudo apt list --upgradable`|  listing all upgradable packages
|`sudo apt full-upgrade -y `| upgrading all applications
|`sudo apt remove apache2`|removing a package
|`sudo apt purge apache2`| removing a package and its configurations
|`sudo apt autoremove`|  removing dependencies that are not needed anymore
|`sudo apt clean`|  removing the saved deb files from the cache directory (var/cache/apt/archives)
|`sudo apt show nginx`|showing information about a package
|`sudo apt list --installed`| listing all installed packages

##### listing all available packages
`sudo apt list`

`sudo apt list | wc -l`
 
##### searching for a package
`sudo apt list | grep nginx`



