---
title: Port Scanning
type: handbook
prev: handbook/port-scanning/
---

#### Discovering Open TCP Ports

| Command                                                                                          | Description           |
|--------------------------------------------------------------------------------------------------|-----------------------|
| `sudo nmap <target> --top-ports=10`                                                              | Top 10 TCP Ports      |
| `sudo nmap <target> -p- --packet-trace -Pn -n --disable-arp-ping`                                | Tracing the Packets   |
| `sudo nmap <target> -p- --packet-trace --disable-arp-ping -Pn -n --reason -sT`                   | Connect Scan          |

#### Discovering Open UDP Ports

| Command                                                                 | Description     |
|-------------------------------------------------------------------------|-----------------|
| `sudo nmap <target> -F -sU`                                             | UDP Port Scan   |

#### Saving the Results in Different Formats

| Command                                            | Description                  |
|----------------------------------------------------|------------------------------|
| `sudo nmap <target> -p- -oA target`                | Saves the results in all formats |
| `cat target.nmap`                                  | Normal Output                |
| `cat target.gnmap`                                 | Grepable Output              |
| `cat target.xml`                                   | XML Output                   |
| `xsltproc target.xml -o target.html`               | Style Sheets (XML to HTML)   |
