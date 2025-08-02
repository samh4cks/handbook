---
title: Nmap Scripting Engine
type: handbook
prev: handbook/nmap-scripting/
weight: 4
---
---

Nmap Scripting Engine (NSE) is another handy feature of Nmap. It provides us with the possibility to create scripts in Lua for 
interaction with certain services. 


| Category   | Description                                                                                                                             |
|------------|-----------------------------------------------------------------------------------------------------------------------------------------|
| auth       | Determination of authentication credentials.                                                                                            |
| broadcast  | Scripts, which are used for host discovery by broadcasting and the discovered hosts, can be automatically added to the remaining scans. |
| brute      | Executes scripts that try to log in to the respective service by brute-forcing with credentials.                                        |
| default    | Default scripts executed by using the -sC option.                                                                                       |
| discovery  | Evaluation of accessible services.                                                                                                      |
| dos        | These scripts are used to check services for denial of service vulnerabilities and are used less as it harms the services.              |
| exploit    | This category of scripts tries to exploit known vulnerabilities for the scanned port.                                                   |
| external   | Scripts that use external services for further processing.                                                                              |
| fuzzer     | This uses scripts to identify vulnerabilities and unexpected packet handling by sending different fields, which can take much time.     |
| intrusive  | Intrusive scripts that could negatively affect the target system.                                                                       |
| malware    | Checks if some malware infects the target system.                                                                                       |
| safe       | Defensive scripts that do not perform intrusive and destructive access.                                                                 |
| version    | Extension for service detection.                                                                                                        |
| vuln       | Identification of specific vulnerabilities.                                                                                             |


| Commands                                       | Description                   |
|------------------------------------------------|-------------------------------|
| `sudo nmap <target> -sC`                       | Default Scripts               |
| `sudo nmap <target> --script <category>`       | Specific Scripts Category     |
| sudo nmap <target> -p <port> -A                | Aggressive Scan               |
| sudo nmap <target> -p <port> -sV --script vuln | Vuln Category                 |


