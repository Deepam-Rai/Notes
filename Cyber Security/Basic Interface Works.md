
| Command | Purpose |
| -- | -- |
| `ifconfig` | current network config |
| `iwconfig` | current wired connections |

### Changing mac address
Using `ifconfig`:
```shell
ifconfig <interface> down;
ifconfig <interface> hw ether <ne:w:v:al:ue>;
ifconfig <interface> up;
```
- reverts back on reboot.
- `ifconfig` is deprecated, in favor of `ip`  and doesn't come pre-installed in Debian now.

Using `ip`:
```shell
ip link dev set <interface> down;
ip link dev set address <interface> <ne:wm:ac:ad:dr:es>;
ip link dev set <interface> up;
```

### Setting to monitor mode
```shell
ifconfig <interface> down;
airmon-ng check kill; #not compulsory; killing process that may interfere
iwconfig <interface> mode monitor;
ifconfig <interface> up
```
