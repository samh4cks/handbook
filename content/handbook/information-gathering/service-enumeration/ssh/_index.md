---
title: SSH (22)
type: handbook
weight: 2
---
---

### Cheat sheet 

| Command                                                                                                         | Description                                       |
|-----------------------------------------------------------------------------------------------------------------|---------------------------------------------------|
| `nmap -sV -p22 <target>`                                                                                        | Detect SSH service/version                        |
| `nmap --script ssh-hostkey -p22 <target>`                                                                       | Grab SSH public keys                              |
| `nmap --script ssh-auth-methods -p22 <target>`                                                                  | Check auth mechanisms (publickey, password)       |
| `hydra -l root -P rockyou.txt ssh://<target>`                                                                   | Brute-force SSH login                             |
| `ncrack -p 22 -U users.txt -P pass.txt <target>`                                                                | Multi-user brute-force using Ncrack               |
| `ssh -v user@<target>`                                                                                          | Connect via SSH (verbose)                         |
| `ssh -v <user>@<target> -o PreferredAuthentications=password`                                                   | Preferred authentication method                   |
| `ssh -i key.pem user@<target>`                                                                                  | Connect using a private key                       |
| `scp file.txt user@<target>:/tmp/`                                                                              | Secure file transfer                              |
| `ssh -J jump@<pivot> target@<internal>`                                                                         | SSH pivoting using ProxyJump                      |
| `ssh -oProxyCommand="nc -X 5 -x 127.0.0.1:9050 %h %p" user@<target>`                                            | Connect over proxychains                          |

### NSE Scripts

`find / -type f -name "*ssh*" | grep nmap/scripts`

```/usr/share/nmap/scripts/ssh-hostkey.nse
/usr/share/nmap/scripts/ssh-auth-methods.nse
/usr/share/nmap/scripts/ssh-brute.nse
/usr/share/nmap/scripts/ssh-run.nse
/usr/share/nmap/scripts/sshv1.nse
```

**SSH (Secure Shell)** is a cryptographic network protocol used to securely access and manage remote systems over an unsecured network.
It provides encrypted authentication, remote shell access, and secure file transfers. SSH replaced older insecure protocols like Telnet and RSH.
