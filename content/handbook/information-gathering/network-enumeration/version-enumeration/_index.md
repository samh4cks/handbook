---
title: Version Enumeration
type: handbook
prev: handbook/version-enumeration/
weight: 3
---
---
It is essential to determine the application and its version as accurately as possible. We can use this information to scan for known vulnerabilities 
and analyze the source code for that version if we find it.


| Commands                                                               | Description                    |
|------------------------------------------------------------------------|--------------------------------|
| `sudo nmap <target> -p- -sV`                                           | Version Scan & Banner Grabbing |
| `sudo nmap <target> -p- -sV -v`                                        | Verbosity Level                |
| `sudo tcpdump -i eth0 host <attacker> and <target>`                    | Tcpdump                        |
| `nc -nv <target> <port>`                                               | Netcat                         |

