## Service Management using systemd and systemctl
===================================================
| command | Description     |
| :-------- | :------- | 
| `systemd-analyze` | showing info about the boot process
| `systemd-analyze blame` | 
| listing all active units systemd knows about
| `systemctl list-units` |
|`systemctl list-units` | `grep ssh`|
|`sudo systemctl status nginx.service`| checking the status of a service
|`sudo systemctl stop nginx`| stopping a service
|`sudo systemctl start nginx`| starting a service
|`sudo systemctl restart nginx`| restarting a service
|`sudo systemctl reload nginx`| reloading the configuration of a service
|`sudo systemctl reload-or-restart nginx`| ""
|`sudo systemctl enable nginx`|  enabling to start at boot time
|`sudo systemctl disable nginx`| disabling at boot time
|`sudo systemctl is-enabled nginx`| checking if it starts automatically at boot time
|`sudo systemctl mask nginx`| masking a service (stopping and disabling it)
|`sudo systemctl unmask nginx`| unmasking a service
