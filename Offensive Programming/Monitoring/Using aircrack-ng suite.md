
### Setting to monitor mode
#### Checking available network interfaces
```shell
sudo airmon-ng
```

#### Put the interface in monitor mode
```shell
sudo airmon-ng start <interface>
```
Renames interface. Use the new name further ahead.

## Start dump
```shell
sudo airodump-ng <interface>
```

## Common airodump flags

### Flags while starting airodump
```shell
sudo airodump-ng <interface> ...flags and values...
```

| Flags       | Use                          |
| ----------- | ---------------------------- |
| `-c`        | Specify channel              |
| `-bssid`    | Specify bssid                |
| `-w <name>` | Capture the output to files. |
| `-b`        | Specify bands to monitor     |
|             |                              |

### Key commands used while airodump is running

| Key Commands | Use                                                                            |
| ------------ | ------------------------------------------------------------------------------ |
| `tab`        | Make the dump list interactive                                                 |
| `a`          | Filter only stations, devices, etc                                             |
| `m`          | Color code selected AP, use `tab` first                                        |
| `s`          | Sort by different column in dump. The corresponding column is indicated on top |
| `p`          | Disable colored display                                                        |
|              |                                                                                |

----
# airgraph-ng
Helps visualize the captures from airodump-ng as graph.

Installation:
```shell
sudo apt install airgraph-ng
```

Use:
```shell
sudo airgraph-ng -l <capturefile>.csv -o <outputImage>.png -g <type of view>
```

| flag      | Type of view                                   |
| --------- | ---------------------------------------------- |
| `-g CAPR` | Captured network stations and hosts connected. |
| `-g CPG`  | Un-connected devices.                          |
|           |                                                |

----
