
## `systemd`
- More control than `cron`. But also more complicated.

Create timer:
1. Create `<name>.timer` file in `/etc/systemd/system`.
2. Create `<name>.service` file in `/etc/systemd/system`.

Start timer:
```shell
# Reload daemon after creating the timer
sudo systemctl daemon-reload
# Enable timer
sudo systemctl enable <name>.timer
# start timer
sudo systemctl start <name>.timer
# restart timer
sudo systemctl restart <name>.timer

# check status
sudo systemctl status <name>.timer
# get timer logs
sudo journalctl -u <name>.service
```

`/etc/systemd/system/<name>.timer` file format:
```sh
[Unit]
Description=About the timer.

[Timer]
OnCalendar=Fri 2012-11-23 11:11:13 # day year-month-date hour:min:sec
Persistent=true
unit=<name>.service

[Install]
WantedBy=multi-user.target
```
- can use `*` as wildcard in `OnCalendar`. `man systemd.time` for more help.

`/etc/systemd/system/<name>.service` file format:
```sh
[Unit]
Description=About the job.

[Service]
Type=simple
Restart=always
ExecStart=/bin/bash /full/path/to/script.sh
```
- Can specify `/bin/bash` or `/usr/bin/python3`, etc.


----
## `cron`

- `crond` daemon enables cron functionality.
- File locations:
	- `/var/spool/cron/crontabs`: Individual user cron files.
	- `/etc/cron.d`: System services and applications cron files.
	- `/etc/anacrontab`: `anacron` related.
- `/etc/cron.allow`: List of all users with permission to create cron jobs.

```shell
crontab -e  # create/edit cron table

# Example of job definition: 
# .---------------- minute (0 - 59) 
# | .------------- hour (0 - 23) 
# | | .---------- day of month (1 - 31) 
# | | | .------- month (1 - 12) OR jan,feb,mar,apr ... 
# | | | | .---- day of week (0 - 6) (Sunday=0 or 7) OR sun,mon,...,sat 
# | | | | | 
# * * * * * <command to be executed>

# check logs
grep CRON /var/log/syslog


# logging output with tags in syslog
* * * * * <command> | logger -t <tag>
# checking logs with tags
grep <tag> /var/log/syslog
```


----
