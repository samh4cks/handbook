---
title: Web Enumeration
type: handbook
weight: 4
---
---

Web Reconnaissance is the foundation of a thorough security assessment. This process involves systematically and meticulously collecting information about a target website or web application.

The primary goals of web reconnaissance include:

• Identifying Assets: Uncovering all publicly accessible components of the target, such as web pages, subdomains, IP addresses, and technologies used. This step provides a comprehensive overview of the target's online presence.<br>

• Discovering Hidden Information: Locating sensitive information that might be inadvertently exposed, including backup files, configuration files, or internal documentation. These findings can reveal valuable insights and potential entry points for attacks.<br>

• Analysing the Attack Surface: Examining the target's attack surface to identify potential vulnerabilities and weaknesses. This involves assessing the technologies used, configurations, and possible entry points for exploitation.<br>

• Gathering Intelligence: Collecting information that can be leveraged for further exploitation or social engineering attacks. This includes identifying key personnel, email addresses, or patterns of behaviour that could be exploited.<br>

### Active Reconnaissance

| Technique             | Description                                                                                      | Example                                                                                     | Tools                                     | Risk of Detection                                                                 |
|-----------------------|--------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------|--------------------------------------------|-----------------------------------------------------------------------------------|
| Port Scanning         | Identifying open ports and services running on the target.                                       | Using Nmap to scan a web server for open ports like 80 (HTTP) and 443 (HTTPS).              | Nmap, Masscan, Unicornscan                | High: Direct interaction with the target can trigger IDS and firewalls.           |
| Vulnerability Scanning| Probing the target for known vulnerabilities, such as outdated software or misconfigurations.    | Running Nessus against a web app to check for SQLi or XSS flaws.                           | Nessus, OpenVAS, Nikto                     | High: Scanners send exploit payloads that security solutions can detect.          |
| Network Mapping       | Mapping the target's network topology, including connected devices and their relationships.      | Using traceroute to find packet paths and network hops to a target server.                  | Traceroute, Nmap                           | Medium to High: Unusual traffic may raise suspicion.                              |
| Banner Grabbing       | Retrieving info from banners displayed by services on the target.                                | Connecting to port 80 and examining the HTTP response headers.                              | Netcat, curl                                | Low: Minimal interaction but still potentially logged.                            |
| OS Fingerprinting     | Identifying the OS running on the target system.                                                  | Using `nmap -O` to detect if the target runs Linux or Windows.                              | Nmap, Xprobe2                              | Low: Usually passive, but some methods may trigger alerts.                        |
| Service Enumeration   | Identifying the versions and details of services on open ports.                                  | Using `nmap -sV` to see if Apache 2.4.50 or Nginx 1.18.0 is running.                         | Nmap                                        | Low: May be logged, but rarely triggers alerts.                                   |
| Web Spidering         | Crawling websites to find directories, files, and parameters.                                    | Using Burp Spider or ZAP to discover hidden paths or admin panels.                          | Burp Suite Spider, OWASP ZAP Spider, Scrapy| Low to Medium: Poorly configured crawlers can draw attention.                     |

### Passive Reconnaissance

| Technique             | Description                                                                 | Example                                                                                             | Tools                                                                 | Risk of Detection                          |
|----------------------|-----------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------|--------------------------------------------|
| Search Engine Queries | Using search engines to find information about the target.                  | Searching Google for "[Target Name] employees" to gather details from public web pages.            | Google, DuckDuckGo, Bing, Shodan, Censys                             | Very Low: Normal browsing behavior.        |
| WHOIS Lookups         | Querying WHOIS databases for domain registration details.                   | WHOIS lookup to find a domain’s registrant name and contact info.                                  | `whois`, online WHOIS lookup tools                                   | Very Low: Passive, non-intrusive.          |
| DNS Enumeration       | Inspecting DNS records to discover subdomains and services.                 | Using `dnsenum` to identify subdomains and associated infrastructure.                              | `dig`, `host`, `nslookup`, `dnsenum`, `fierce`, `dnsrecon`           | Very Low: DNS lookups are standard traffic.|
| Web Archive Analysis  | Checking historical snapshots of websites for leaked or outdated info.      | Exploring Wayback Machine for a site’s earlier pages and exposed paths.                            | Wayback Machine, `archive.org`                                       | Very Low: Archival browsing is passive.    |
| Social Media Analysis | Mining social platforms for employee roles, structure, or targets.          | Searching LinkedIn for staff info to build a profile for social engineering.                       | LinkedIn, Twitter, Facebook, Maltego, SpiderFoot                     | Very Low: Public data, not suspicious.     |
| Code Repositories     | Searching public repos for secrets, tokens, or vulnerable code.             | Looking up exposed `.env` files or hardcoded keys in GitHub repos.                                 | GitHub, GitLab, GitHub Dorks, truffleHog, GitLeaks                  | Very Low: Public repos are open to search. |
