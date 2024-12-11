
Linux follows Filesystem Hierarchy Standard: https://www.pathname.com/fhs  

Filesystem Hierarchy:

| Path     | Description                                             |
| -------- | ------------------------------------------------------- |
| `/`      | Root folder.                                            |
| `/bin`   | Essential command binaries.                             |
| `/sbin`  | Essential system binaries.                              |
| `/boot`  | Static files of the bootloader.                         |
| `/dev`   | Device (hardware) files.                                |
| `/etc`   | System configuration.                                   |
| `/lib`   | Essential shared libraries and kernel modules.          |
| `/var`   | Variable files. e.g., log files, cron files, etc.       |
| `/tmp`   | Temporary files.                                        |
| `/media` | Mount point for removable media.                        |
| `/mnt`   | Mountpoint for mounting a filesystem temporarily.       |
| `/usr`   | Contains user-installed and system-wide read-only data. |
| `/root`  | Home directory for root user.                           |
| `/home`  | A dedicated directory for each user on the system       |
| `/opt`   | Add-on application software packages.                   |

`/mnt` vs `/media`:

| Feature  | `/mnt`                         | `/media`                             |
| -------- | ------------------------------ | ------------------------------------ |
| Purpose: | Manual, temporary mounts.      | Automatic mounts of removable media. |
| Usage:   | System administraion, testing. | Day-to-day dynamic mounting.         |
