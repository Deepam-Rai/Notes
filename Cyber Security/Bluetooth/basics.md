- hcitool is deprecated. bluetoothctl new one.  


## List Interfaces
```shell
hciconfig
```
## Scanning
- Turn on Bluetooth.
- Replace `hci0` with required interface.

```shell
hciconfig hci0 up
hcitool -i hci0 scan
```

```shell
bluetoothctl scan on
```

## Remote device info
```shell
sudo sdptool browse <mac-address>
```
