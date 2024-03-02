# Commonly used flags

| flag              | Use                                                                                                      |
| ----------------- | -------------------------------------------------------------------------------------------------------- |
| `-n`              | No DNS resolution                                                                                        |
| `-s<scan type>`   | eg. `sn`, `sL`, etc.                                                                                     |
| `-o<output type>` | eg. `oN`, `oX`, etc.                                                                                     |
| `-p`              | Selecting ports to scan                                                                                  |
| `--top-ports`     | For top `x` ports                                                                                        |
| `-v`              | verbose                                                                                                  |
| `-O`              | OS detection                                                                                             |
| `-A`              | Aggressive/Advanced scan                                                                                 |
| `-T`              | Set timing template. `paranoid(0), sneaky(1), polite(2), normal (3), aggressive(4), insane(5)`. eg `-T4` |
| `-sT`             | TCP connect scan                                                                                         |
| `-sU`             | UDP connect scan                                                                                         |
| `-sV`             | Version detection                                                                                        |
| `--script`        | Run pre-defined scripts. eg `--script vuln` run all pre-defined vulnerability test scripts in NSE.       |

----

# Ways of specifying IP addresses

| way of specifying                 | addresses specified                  |
| --------------------------------- | ------------------------------------ |
| `<ip address>`                    | Single host                          |
| `<ip address>/<mask>`             | Whole subnet                         |
| `<ip adderss1> <ip address2> ...` | Multiple specified addresses         |
| `a.b.c.1,2,3,4`                   | `a.b.c.1`, `a.b.c.2`, `a.b.c.3`, ... |
| `a.b.c.x-y`                       | `a.b.c.x`, ..., `a.b.c.y`            |
| `a.b.c.*`                         | `*` wildcard denoting all            |
| `--exclude <ip address>`          | Exclude from scan.                   |
| `-iL file.txt`                    | Addresses in the file.               |


----
# Common Scans
#### Basic scan against a host
```
nmap <ip address>
nmap <hostname>
```

#### Normal ping scan without DNS resolution
```
nmap -sn <ip address>/<mask>
```
- Hosts often block IP based ping packets.

#### ARP scans
```

```


#### Port scan
```
nmap -p <port no> <ip address>   // single port
nmap -p x-y <ip address>         // port in range x-y
nmap --top-ports <x> <ip address> // top x ports
```


#### OS detection
```
nmap -O <ip address>
```


# Pre-defined scripts
nmap can run predefined set scripts. Own scripts can be written in Lua. 
```
nmap --scripts <script name> <ip address> 
nmap --scripts vuln <ip address> // run all vulnerability test scripts in NSE
```

There are predefined scripts for attacking too.

----
# Host discovery

```bash
sudo nmap -PR -sn <ip address>/<mask>
```

IP address/network route can be found using command `route` or `ifconfig`.  
- sends ARP requests.

```shell
sudo nmap -PE -sn <ip address>/<mask>
```
- sends ICMP packets.
- Not reliable as many firewalls just drop these packets.

```shell
sudo nmap -PA80 -sn <ip address>/<mask>
```
- sends ACK(Acknowledgement) packets.

  
<hr>

# Detecting malware infections on remote hosts
This can be done using pre-defined scripts. Runs extensive tests on backdoors.  
e.g., common malware detection
```
nmap -sV --script=http-malware-host 192.168.1.105
```

---
# ZenMap - GUI nmap
https://nmap.org/zenmap/

----
