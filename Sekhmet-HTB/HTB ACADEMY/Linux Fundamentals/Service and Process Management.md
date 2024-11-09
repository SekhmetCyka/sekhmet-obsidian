In general, there are two types of services: internal, the relevant services that are required at system startup, which for example, perform hardware-related tasks, and services that are installed by the user, which usually include all server services. Such services run in the background without any user interaction. These are also called `daemons` and are identified by the letter '`d`' at the end of the program name, for example, `sshd` or `systemd`.

| Command                               | Description                                  |
| ------------------------------------- | -------------------------------------------- |
| `systemctl`                           | Start a program                              |
| `systemctl status`                    | Check if the program is runing wihtout error |
| `systemctl enable [ssh]`              | Add the prog to SysV (laucnch at start)      |
| `systemctl list-units --type=service` | List all prog that are runing                |

## Kill a Process

A process can be in the following states:

- Running
- Waiting (waiting for an event or system resource)
- Stopped
- Zombie (stopped but still has an entry in the process table).


Processes can be controlled using `kill`, `pkill`, `pgrep`, and `killall`. To interact with a process, we must send a signal to it. We can view all signals with the following command

The most commonly used are

|**Signal**|**Description**|
|---|---|
|`1`|`SIGHUP` - This is sent to a process when the terminal that controls it is closed.|
|`2`|`SIGINT` - Sent when a user presses `[Ctrl] + C` in the controlling terminal to interrupt a process.|
|`3`|`SIGQUIT` - Sent when a user presses `[Ctrl] + D` to quit.|
|`9`|`SIGKILL` - Immediately kill a process with no clean-up operations.|
|`15`|`SIGTERM` - Program termination.|
|`19`|`SIGSTOP` - Stop the program. It cannot be handled anymore.|
|`20`|`SIGTSTP` - Sent when a user presses `[Ctrl] + Z` to request for a service to suspend. The user can handle it afterward.|