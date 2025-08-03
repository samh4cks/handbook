---
title: Subdomain Bruteforcing
type: handbook
weight: 3
---
---

### Cheat sheet

| Command                                                                                                                                                 | Description                                                                                       |
|---------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------|
| `dnsenum --enum inlanefreight.com -f /usr/share/seclists/Discovery/DNS/subdomains-top1million-110000.txt -r` | Performs DNS enumeration on `inlanefreight.com`, using a custom wordlist for brute-forcing subdomains (`-f`) and enables recursive subdomain brute-forcing (`-r`). |

**Subdomain Brute-Force Enumeration** is a powerful active subdomain discovery technique that leverages pre-defined lists of potential subdomain names. 

| Tool         | Description                                                                                                                                                    |
|--------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| dnsenum      | Comprehensive DNS enumeration tool that supports dictionary and brute-force attacks for discovering subdomains.                                              |
| fierce       | User-friendly tool for recursive subdomain discovery, featuring wildcard detection and an easy-to-use interface.                                              |
| dnsrecon     | Versatile tool that combines multiple DNS reconnaissance techniques and offers customizable output formats.                                                   |
| amass        | Actively maintained tool focused on subdomain discovery, known for its integration with other tools and extensive data sources.                              |
| assetfinder  | Simple yet effective tool for finding subdomains using various techniques, ideal for quick and lightweight scans.                                             |
| puredns      | Powerful and flexible DNS brute-forcing tool, capable of resolving and filtering results effectively.                                                         |
