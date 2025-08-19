
> **daemons**: A computer program that runs in background and wakes up to handle periodic service requests.

- Mostly daemons have process name ending in `d`, e.g., `systemd`.

Tools:
- `systemctl`: Query or send control commands to the system manager.
- `journalctl`: Query the journal, kind of logs.
- `jobs`: Display status of jobs.
- `bg`: Move job to background. Not interactive in terminal, only output results are shown.
- `fg`: Move job to the foreground. Interactive in terminal.

## Process
Process states:
- **Running**
- **Waiting**: for an event or a system resource.
- **Stopped**
- **Zombie**: Stopped but still has entry in process table.

To kill a process we send signal to the process.  
```shell
# list all signal names
kill -l

# immediately kill a process using Process ID
kill 9 <PID>
```

Commonly used signals:

| Signal | Name      | Description                                                                                    |
| ------ | --------- | ---------------------------------------------------------------------------------------------- |
| `1`    | `SIGHUP`  | Sent to process when terminal that controls it is closed                                       |
| `2`    | `SIGINT`  | Sent when user presses `Ctrl + C` to interrupt                                                 |
| `3`    | `SIGQUIT` | Sent when user presses `Ctrl + D` to quit                                                      |
| `9`    | `SIGKILL` | Kill immediately with no clean-up operations                                                   |
| `15`   | `SIGTERM` | Program terminate                                                                              |
| `19`   | `SIGSTOP` | Stop the program, cannot be handled anymore                                                    |
| `20`   | `SIGTSTP` | Sent when user presses `Ctrl + Z` to request for service to suspend. Can be handled afterward. |

```shell
# run process in background
<command> &

# Ececuting multiple commands
# Run one after other; irrespective of status of last command
<command1> ; <command2> ; ...
# Run following command only if previous command was success
<command1> && <command2> && ...
# Use the STDOUT of a command as input in following command
<command1> | <command2> | ...
```

