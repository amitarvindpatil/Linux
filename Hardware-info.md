## Getting System Hardware Information
===================================================
| command | Description     |
| :-------- | :------- | 
| `lshw` | displaying full hardware information
| `lshw -short` | short format
| `lshw -json` | json format
| `lshw -html` | html format
|----------------------------------|
|`inxi -Fx`| 
|`lscpu`| displaying info about the CPU
|`lscpu -C cpu`| 
|`lscpu -J`| Json Format
| displaying info about the installed RAM memory |
|`dmidecode -t memory`|
|dmidecode -t memory | grep -i size|
|`"dmidecode -t memory | grep -i max"`|
|`free -m`| displaying info about free/used memory
|getting info about pci buses and about the devices connected to them|
|`lspci`|
|`lspci | grep -i wireless`|
|`lspci | grep -i vga`|
|getting info about USB controllers and about devices connected|
|`lsusb`|
|`lsusb -v`|
|getting info about hard disks|
|`lshw -short -C disk`|
|`fdisk -l`|
|`fdisk -l /dev/sda`|
|`lsblk`|
|`hdparm -i /dev/sda`|
|`hdparm -I /dev/sda`|
|benchmarking disk read performance|
|`hdparm -tT --direct /dev/sda`|
|getting info about WiFi cards and networks|
|`lshw -C network`|
|`iw list`|
|`iwconfig`|
|`iwlist wlo1 scan`|
|Getting hardware information from the /proc virtual fs|
|`cat /proc/cpuinfo`|
|`/proc/partitions`|
|`cat /proc/meminfo`|
|`cat /proc/version`|
|`uname -r`| kernel version
|`uname -a`|
|`acpi -bi`| battery information
|`acpi -V`|
|Working directly with device files (dd)|
|`dd if=/dev/sda of=~/mbr.dat bs=512 count=1`|backing up the MBR (the first sector of /dev/sda)
|`dd if=~/mbr.dat of=/dev/sda bs=512 count=1`| restoring the MBR
|`dd if=/dev/sda1 of=/dev/sdb2 bs=4M status=progress`| cloning a partition (sda1 to sdb2)


