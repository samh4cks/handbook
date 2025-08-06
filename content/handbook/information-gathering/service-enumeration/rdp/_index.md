---
title: RDP (3389)
type: handbook
weight: 17
---
---

### Cheat sheet 

| Command                                                                 			 | Description                                 |
|------------------------------------------------------------------------------------|---------------------------------------------|
| `nmap -p3389 -sV <target>`                                              			 | Detect RDP service and version              |
| `nmap -p3389 --script rdp-enum-encryption <target>`                     			 | Check supported RDP encryption methods      |
| `nmap -p3389 --script rdp-ntlm-info <target>`                           			 | Pull NTLM domain, user, and workgroup info  |
| `ncrack -p 3389 -U users.txt -P pass.txt <target>`                      			 | Brute-force RDP credentials using Ncrack    |
| `hydra -t 4 -V -f -u -l <user> -P rockyou.txt rdp://<target>`            			 | Brute-force RDP using Hydra                 |
| `xfreerdp /u:<user> /p:<pass> /v:<target>`                                         | Connect using FreeRDP                       |
| `rdesktop -u <user> -p <pass> <target>`                                            | Legacy RDP client (may still work)          |
| `rdpscan <target>`                                                                 | Scan for RDP-related CVEs and version info  |
| `xfreerdp /u:<user> /p:<pass> /v:<target> /drive:<path-to-directory>,<share-name>` | Uploading a share using RDP                 |

### NSE Scripts

`find / -type f -name rdp* 2>/dev/null | grep scripts`

```/usr/share/nmap/scripts/rdp-enum-encryption.nse
/usr/share/nmap/scripts/rdp-ntlm-info.nse
```

RDP is a Microsoft protocol for remote graphical access to a desktop or server.

It's commonly used for administration, especially on Windows systems.

Some Linux systems (with xrdp) also expose RDP.

• Port: 3389/TCP<br>
• Auth: NTLM or Kerberos (via AD)<br>
• Encryption: SSL/TLS or CredSSP<br>
• Usage: Admin access, remote desktops, remote app access



