## Getting info about the network interfaces (ifconfig, ip, route)
==================================================================
| command | Description     |
| :-------- | :------- | 
|`ifconfig`|displaying information about enabled interfaces
|`ifconfig -a`|displaying information about all interfaces (enabled and disabled)
|`ip address show`|
|displaying info about a specific interface|
|`ifconfig enp0s3`|
|`ip addr show dev enp0s3`|
|`ip -4 address`| showing only IPv4 info
|`ip -6 address`| showing only IPv6 info
|displaying L2 info (including the MAC address)|
|`ip link show`|
|`ip link show dev enp0s3`|
|displaying the default gateway|
|`route`|
|`route -n`| numerical addresses
|`ip route show`|
|`resolvectl status`| displaying the DNS servers

## Setting the network interfaces (ifconfig, ip, route)
=========================================================================
| command | Description     |
| :-------- | :------- | 
|disabling an interface|
|`ifconfig enp0s3 down`| ip link set enp0s3 down
|activating an interface|
|`ifconfig enp0s3 up`| ip link set enp0s3 up
|checking its status|
|`ifconfig -a`| ip link show dev enp0s3
|setting an ip address on an interface|
|`ifconfig enp0s3 192.168.0.222/24 up`|
|`ip address del 192.168.0.111/24 dev enp0s3`|
|`ip address add 192.168.0.112/24 dev enp0s3`|
|`ifconfig enp0s3:1 10.0.0.1/24`|setting a secondary ip address on sub-interface 
|deleting and setting a new default gateway|
|`route del default gw 192.168.0.1`|
|`route add default gw 192.168.0.2`|
|deleting and setting a new default gateway|
|`ip route del default`|
|`ip route add default via 192.168.0.1`|
|changing the MAC address|
|`ifconfig enp0s3 down`|
|`ifconfig enp0s3 hw ether 08:00:27:51:05:a1`|
|`ifconfig enp0s3 up`|
|`ip link set dev enp0s3 address 08:00:27:51:05:a3`| changing the MAC address

## Network Static configuration using Netplan (Ubuntu)
=========================================================================
| command | Description     |
| :-------- | :------- | 
|Stop and disable the Network Manager|
|`sudo systemctl stop NetworkManager`|
|`sudo systemctl disable NetworkManager`|
|`sudo systemctl status NetworkManager`|
|`sudo systemctl is-enabled NetworkManager`|


# 2. Create a YAML file in /etc/netplan
 
|` network:
   version: 2
   renderer: networkd
   ethernets:
     enp0s3:
       dhcp4: false
       addresses:
         - 192.168.0.20/24
       gateway4: "192.168.0.1"
       nameservers:
         addresses:
           - "8.8.8.8"
           - "8.8.4.4" `|

| command | Description     |
| :-------- | :------- | 
|`sudo netplan apply`|Apply the new config
|Check the configuration|
|`ifconfig`|
|`route -a`|