Getting details:
```shell
# list users
getent passwd

# list groups
getent group

# all groups with a specific user
getent group | grep <user>

# get uid and gid and groups of a user
id <username>
```

Adding user:
```shell
# adding user
# 1) using adduser (recommended)
sudo adduser <username>  # will prompt to enter further details
# 2) using useradd
sudo useradd <username> -m -c "About user"
sudo passwd <username> # set passwd

# modifying user account
sudo usermod <username> <options>
```
- `-p` in `useradd` expects encrypted password. Setting later is easier.

Deleting user:
```shell
sudo userdel <username> -rf
```

Using `su`:
```shell
su <username>  # to login as that username
su -c <command> <username>  # run command as that username
# example: su -c 'ls /home/<username>' <username>

```