---
title: Host Discovery
type: handbook
prev: handbook/network-enumeration/
---

### Cheatsheet

| Command                                                                                                             | Description                              |
|---------------------------------------------------------------------------------------------------------------------|------------------------------------------|
| `sudo nmap 10.10.1.0/24 -sn -oA tnet \| grep for \| cut -d" " -f5`                                                  | Scanning a network range                 |
| `sudo nmap -sn -oA tnet -iL hosts.lst \| grep for \| cut -d" " -f5`                                                 | Scanning IP list                         |
| `sudo nmap -sn -oA tnet <target1> <target2> <target3> \| grep for \| cut -d" " -f5`                                 | Scanning multiple IPs                    |
| `sudo nmap <target> -sn -oA host`                                                                                   | Scan a single IP                         |
| `sudo nmap <target> -sn -oA host -PE --packet-trace`                                                                | To see all packets sent and received     |
| `sudo nmap <target> -sn -oA host -PE --packet-trace --disable-arp-ping`                                             | Disable ARP ping                         |


Resources - 

Identifying OS based on TTL (Time-to-live) - [TTL](https://subinsb.com/default-device-ttl-values/)

