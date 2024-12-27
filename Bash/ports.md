Check if port is being used:
```shell
netstat -tuln | grep ':8082'
```

List all listening ports:
```shell
netstat -tuln | grep LISTEN
```
