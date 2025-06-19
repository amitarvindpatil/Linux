## Cron Commands -> Task Scheduling using Cron
===================================================
| command | Description     |
| :-------- | :------- | 
| `crontab -e` | editing the current user’s crontab file 
| `crontab -l` | listing the current user’s crontab file 
| `crontab -r` | removing the current user’s crontab file 
| Common Examples
| `* * * * * /path_to_task_to_run.sh` | run every minute
| `15 * * * * /path_to_task_to_run.sh` | run every hour at minute 15
| `30 18 * * * /path_to_task_to_run.sh` | run every day at 6:30 PM
| `3 22 * * 1 /path_to_task_to_run.sh` | run every Monday at 10:03 PM
| `10 6 1 * * /path_to_task_to_run.sh` | run on the 1st of every Month at 6:10 AM
| `1,20,35 * * * * /path_to_task_to_run.sh` | run every hour at minute 1, 20 and 35
| `10 */2 * * * /path_to_task_to_run.sh` | run every two hour at minute 10
| `@yearly     /path_to_task_to_run.sh` | run once a year on the 1st of January at midnight
| `@monthly    /path_to_task_to_run.sh` | run once a month at midnight on the first day of the month
| `@weekly      /path_to_task_to_run.sh` | run once a week at midnight on Sunday
| `@hourly     /path_to_task_to_run.sh` |  once an hour at the beginning of the hour
| `@reboot     /path_to_task_to_run.sh` | run at boot time
| All scripts in following directories will run as root at that interval:
| `/etc/cron.hourly` |
| `/etc/cron.daily` |
| `/etc/cron.hourly` |
| `/etc/cron.monthly` |
| `/etc/cron.weekly` |
