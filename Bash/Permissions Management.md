- Permissions are assigned to users and groups.
- User can be member of different groups.
- Each file and directory belongs to a specific user and a specific group.

Permissions:
- `r`: Read
- `w`: Write
- `x` Execute
	- Execute permission in a directory do not allow execution of modification of contents within the directory. It only allows to traverse and access the content of directory.


```shell-session
- rwx rw- r--   1 root root 1641 May  4 23:42 /etc/passwd
- --- --- ---   |  |    |    |   |__________|
|  |   |   |    |  |    |    |        |_ Date
|  |   |   |    |  |    |    |__________ File Size
|  |   |   |    |  |    |_______________ Group
|  |   |   |    |  |____________________ User
|  |   |   |    |_______________________ Number of hard links
|  |   |   |_ Permission of others (read)
|  |   |_____ Permissions of the group (read, write)
|  |_________ Permissions of the owner (read, write, execute)
|____________ File type (- = File, d = Directory, l = Link, ... )
```



## Changing permissions
To change the permissions of file/directory.  

References:
- `a`: All users
- `u`: owner;creator
- `g`: group; group of the creator
- `o`: others; everyone outside the group of the creator

Assignment:
- `+`: Grant permission
- `-`: Remove/evoke permission

Permissions:  

| Numerical | Symbolic | permission |
| -- | -- | -- |
|  4 | r | read |
| 2 | w | write |
| 1| x | execute |
| | s | set userid; The executable file when run will run with permission of file owner rather than who launched the executable; When set GUID on directory and file within the directory inherit the group ownership of the directory rather than who created it. |
| | t | sticky bit; when set only the owner or root user can delete or rename the file. |


Use: (Note: The hyphen below has different meaning from minus used to evoke permission.)

| Numerical(Octal Notation) | Symbolic | permission |
| -- | -- | -- |
| 7 | rwx | read,write and execute |
| 6 | rw- | read and write only |
| 5 | r-x | read and execute only |
| 4 | r-- | read only |
| 3 | -wx | write and execute only |
| 2 | -w- | write only |
| 1 | --x | execute only |

Example:
```shell
# read,write, execute permission to all
chmod 777 <file/directory>
chmod +rwx <file/directory>

# read,write,execute permission to user only
chmod 700 <file/directory>
chmod u+rwx,go-rwx <file/directory>
```
- For numerical the digit order is:  chmod  \<user>\<group>\<others>
- `ll <file>`: easy way to check permissions.

## Change owner
```shell
chown <user>:<group> <file/directory>
```

## SUID & SGID
Setting SUID (Set User ID) and SGID (Set Group ID) on a file allows anyone with execute permission to execute it with owner or group's privilege.  
```shell

chmod u+s <file>  # setting suid on executable file
chmod g+s <file>
```
- `s` appears instead of `x` in file listing when these are set.
- If owner/group does not have execute permission then `S` appears instead of `s`.

## sticky bit
Sticky bit are set on directories to ensure that its contents can be deleted and renamed only by owner of the file, owner of the directory or root user.  
```shell
chmod +t <file/directory>  # set sticky bit
```
- `t` appears instead of `x` when this is set.
- If execute permissions are not present then `T` appears instead of `t`.

----
## umask
- used to set the default permissions of the new files/directories.
- umask is restrictive - it denotes which permissions should be removed not which should be granted.

| command | meaning |
| -- | -- |
| umask 002 | others wont have write permission set |
| umask 077 | group and others wont have any permission |

----
