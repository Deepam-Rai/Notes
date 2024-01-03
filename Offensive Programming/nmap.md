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
# Port Scanning
