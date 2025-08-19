Check if port is being used:
```shell
netstat -tuln | grep ':8082'
```

List all listening ports:
```shell
netstat -tuln | grep LISTEN
```

## Forwarding Information Base Prefix Tree
```shell
cat /proc/net/fib_trie

# Example output:
#Main:
#  +-- 0.0.0.0/0 3 0 5
#     |-- 0.0.0.0
#        /0 universe UNICAST
#     +-- 127.0.0.0/8 2 0 2
#        +-- 127.0.0.0/31 1 0 0
#           |-- 127.0.0.0
#              /8 host LOCAL
#           |-- 127.0.0.1
#              /32 host LOCAL
#        |-- 127.255.255.255
#           /32 link BROADCAST
#     +-- 172.17.0.0/16 2 0 2
#        +-- 172.17.0.0/30 2 0 2
#           |-- 172.17.0.0
#              /16 link UNICAST
#           |-- 172.17.0.3
#              /32 host LOCAL
#        |-- 172.17.255.255
#           /32 link BROADCAST
#Local:
#  +-- 0.0.0.0/0 3 0 5
#     |-- 0.0.0.0
#        /0 universe UNICAST
#     +-- 127.0.0.0/8 2 0 2
#        +-- 127.0.0.0/31 1 0 0
#           |-- 127.0.0.0
#              /8 host LOCAL
#           |-- 127.0.0.1
#              /32 host LOCAL
#        |-- 127.255.255.255
#           /32 link BROADCAST
#     +-- 172.17.0.0/16 2 0 2
#        +-- 172.17.0.0/30 2 0 2
#           |-- 172.17.0.0
#              /16 link UNICAST
#           |-- 172.17.0.3
#              /32 host LOCAL
#        |-- 172.17.255.255
#           /32 link BROADCAST
```
