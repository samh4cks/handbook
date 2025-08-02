---
title: Firewall and IDS/IPS Evasion
type: handbook
prev: handbook/firewall/
weight: 6
---
---
### Firewalls

A firewall is a security system that monitors and controls network traffic, allowing or blocking data packets based on predefined rules to prevent unauthorized access and protect against potential threats

### IDS/IPS

IDS detects and reports suspicious network activity, while IPS actively blocks or prevents threats based on attack patterns and signatures.

### Determine Firewalls and Their Rules

Firewalls manage network traffic by allowing, blocking, or restricting connections, which Nmap can test using its scan types. If Nmap finds a port "filtered," it means the firewall either ignored the probe (no response) or actively blocked it (sent an error or reset). Nmap's TCP ACK scan (-sA) sends ACK-flag packets that often bypass firewall rules designed for new connections, helping reveal which traffic firewalls permit or block.


| Commands                                                                    | Description |
| `sudo nmap <target> -p<ports> -sS -Pn -n --disable-arp-ping --packet-trace` | SYN Scan    |
| `sudo nmap <target> -p<ports> -sA -Pn -n --disable-arp-ping --packet-trace` | ACK Scan    |


### Detect IDS/IPS

IDS monitors network traffic and alerts admins of suspicious activity, while IPS actively blocks threats automatically. They’re harder to detect than firewalls because they passively watch traffic. During testing, if an IP used for scanning gets blocked, it indicates IPS presence, so pentesters should scan carefully and use multiple IPs to avoid detection.

### Nmap Decoy Scan (-D):

Uses multiple fake IPs along with your real IP to hide the scan source. Helps bypass IP/subnet blocks and IPS detection. Decoy IPs must be active to avoid triggering security defenses.


| Commands                                                                                          | Description                    |
| `sudo nmap <target> -p<port> -sS -Pn -n --disable-arp-ping --packet-trace -D RND:5`               | Scan using Decoy               |
| `sudo nmap <target> -n -Pn -p<port> -O`                                                           | Testing Firewall Rules         |
| `sudo nmap <target> -n -Pn -p<port> -O -S <diff IP> -e <interface>`                               | Scan using different source IP |
| `sudo nmap <target> -p<port> -sS -Pn -n --disable-arp-ping --packet-trace --source-port 53`       | SYN-Scan from DNS port         |


