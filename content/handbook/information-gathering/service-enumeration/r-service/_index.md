---
title: R-Service (512,513,514)
type: handbook
weight: 11
---
---

### Cheat sheet 


#### R Services Enumeration (rsh, rlogin, rexec)

| Command                                                          | Description                                        |
|------------------------------------------------------------------|----------------------------------------------------|
| `nmap -p 512,513,514 <target>`                                   | Scan for rexec (512), rlogin (513), rsh (514)      |
| `nmap -sV -p 512,513,514 <target>`                               | Service/version detection                          |
| `rlogin -l <user> <target>`                                      | Connect using rlogin                               |
| `rsh <target> -l <user> <command>`                               | Execute remote command via rsh                     |
| `rexec <target>`                                                 | Start interactive rexec session                    |
| `rwho`                                                           | Show logged-in users on local network              |
| `rusers -al <target>`                                            | List users on remote host                          |
| `hydra -l user -P rockyou.txt rsh://<target>`                    | Brute-force rsh (rarely used, low success)         |
| `nmap -p 512 --script rexec-brute <target>`                      | Brute-force rexec credentials                      |
| `nmap -p 514 --script rsh-brute <target>`                        | Brute-force rsh credentials                        |


### NSE Scripts

`find / -type f -name "*r*" 2>/dev/null | grep scripts`

```
/usr/share/nmap/scripts/rexec-brute.nse
/usr/share/nmap/scripts/rsh-brute.nse
```
 
**R Services** are a family of trust-based, plaintext remote shell protocols from early UNIX systems.

These include:

• RSH (Remote Shell) → Port 514<br>
• RLogin → Port 513<br>
• RExec → Port 512<br>

They allow remote shell access without encryption, and often without authentication if the target trusts the source IP and username.

### R Services Overview

| Command  | Service Daemon | Port | Transport Protocol | Description                                                                                                                                                  |
|----------|----------------|------|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `rcp`    | rshd           | 514  | TCP                | Copy files between systems like `cp`, but no prompt before overwriting files. No encryption or authentication beyond `.rhosts` or `hosts.equiv`.            |
| `rsh`    | rshd           | 514  | TCP                | Run remote shell commands without login prompts. Uses `.rhosts` and `hosts.equiv` for trust-based authentication.                                           |
| `rexec`  | rexecd         | 512  | TCP                | Run remote shell commands with username and password sent in plaintext. Trust config may bypass credentials.                                                 |
| `rlogin` | rlogind        | 513  | TCP                | Remote login similar to telnet, but Unix-only. Trust config can bypass login. Passwords sent in cleartext.                                                   |
