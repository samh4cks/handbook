---
title: IPMI (623,634)
type: handbook
weight: 12
---
---

### Cheat sheet 

| Command                                                                                                 | Description                                      |
|---------------------------------------------------------------------------------------------------------|--------------------------------------------------|
| `nmap -sU -p 623 --script ipmi-version <target>`                                                        | Detect IPMI version and check if it's enabled    |
| `nmap -sU -p 623 --script ipmi-info <target>`                                                           | Grab vendor, firmware, and general IPMI info     |
| `ipmitool -I lanplus -H <target> -U <user> -P <pass> chassis status`                                    | Check server power state, temperature, etc.      |
| `ipmitool -I lanplus -H <target> -U <user> -P <pass> sol info`                                          | Fetch Serial-over-LAN configuration              |
| `ipmitool -I lanplus -H <target> -U <user> -P <pass> user list`                                         | Enumerate IPMI users                             |
| `ipmitool -I lanplus -H <target> -U <user> -P <pass> sensor`                                            | View full sensor readings                        |
| `ipmitool -I lanplus -H <target> -U <user> -P <user> power status`                                      | Check system power status                        |
| `ipmi_dumphashes -t <target>`                                                                           | Dump password hashes from vulnerable IPMI        |
| `hydra -l ADMIN -P rockyou.txt -s 623 <target> ipmi`                                                    | Brute-force IPMI credentials                     |
| `metasploit > use auxiliary/scanner/ipmi/ipmi_cipher_zero`                                              | Check for Cipher Zero vulnerability (auth bypass)|
| `metasploit > use auxiliary/scanner/ipmi/ipmi_version`                                                  | Enumerate IPMI version via Metasploit            |
| `metasploit > use auxiliary/scanner/ipmi/ipmi_dumphashes`                                               | Extract IPMI credentials via Metasploit          |


### NSE Scripts

`find / -type f -name "*ipmi*" 2>/dev/null | grep scripts`

```
/usr/share/nmap/scripts/ipmi-cipher-zero.nse
/usr/share/nmap/scripts/ipmi-version.nse
/usr/share/nmap/scripts/ipmi-info.nse
```

**IPMI** is a remote hardware management protocol often implemented in BMCs (Baseboard Management Controllers) on servers.
It allows full out-of-band control — power cycle, hardware sensors, serial console — even if the OS is off.

It uses:
• UDP 623 (main)<br>
• TCP 664 (RMCP+)

