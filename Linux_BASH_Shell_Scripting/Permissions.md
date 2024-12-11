----

# chmod
To change the permissions of file/directory.   

| Symbol | Users |
| -- | -- |
| a | All users |
| u | owner;creator |
| g | group; group of the creator |
| o | others; everyone outside the group of the creator |

| | |
| -- | -- |
| + | Grant permission |
| - | Remove/evoke permission |

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

| Numerical | Symbolic | Purpose |
| -- | -- | -- |
| chmod 777 <file/directory> | chmod +rwx <file/directory> | read,write, execute permission to all |
| chmod 700 <file/directory> | chmod u+rwx,go-rwx <file/directory> | read,write,execute permission to user only |
| chmod 744 <file/directory> | chmod a+r-wx,u+wx <file/directory> | read permission to all. write and execute permission to user only |
| | chmod +t <file/directory>| set sticky bit |
| | chmod u+s \<file> | setting uid on executable file |

- For numerical the digit order is:  chmod  \<user>\<group>\<others>
- `ll <file>`: easy way to check permissions.
----

# umask
- used to set the default permissions of the new files/directories.
- umask is restrictive - it denotes which permissions should be removed not which should be granted.

| command | meaning |
| -- | -- |
| umask 002 | others wont have write permission set |
| umask 077 | group and others wont have any permission |

----
