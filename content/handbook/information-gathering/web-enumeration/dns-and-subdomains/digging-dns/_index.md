---
title: Digging DNS (DNS Tools)
type: handbook
weight: 2
---
---

### Cheat sheet

| Command                                 | Description                                                                                                        |
|-----------------------------------------|--------------------------------------------------------------------------------------------------------------------|
| `dig domain.com`                        | Performs a default A record lookup for the domain.                                                                 |
| `dig domain.com A`                      | Retrieves the IPv4 address (A record) associated with the domain.                                                  |
| `dig domain.com AAAA`                   | Retrieves the IPv6 address (AAAA record) associated with the domain.                                               |
| `dig domain.com MX`                     | Finds the mail servers (MX records) responsible for the domain.                                                    |
| `dig domain.com NS`                     | Identifies the authoritative name servers for the domain.                                                          |
| `dig domain.com TXT`                    | Retrieves any TXT records associated with the domain.                                                              |
| `dig domain.com CNAME`                  | Retrieves the canonical name (CNAME) record for the domain.                                                        |
| `dig domain.com SOA`                    | Retrieves the Start of Authority (SOA) record for the domain.                                                      |
| `dig @1.1.1.1 domain.com`               | Specifies a specific name server to query; in this case 1.1.1.1 (Cloudflare).                                      |
| `dig +trace domain.com`                 | Shows the full path of DNS resolution from root servers down to authoritative servers.                             |
| `dig -x 192.168.1.1`                    | Performs a reverse lookup on the IP to find the associated domain name (PTR record).                               |
| `dig +short domain.com`                 | Provides a short, concise answer to the query.                                                                     |
| `dig +noall +answer domain.com`        | Displays only the answer section of the output.                                                                     |
| `dig domain.com ANY`                    | Attempts to retrieve all available DNS records (often restricted due to RFC 8482).                                 | 


#### DNS Tools

| Tool                     | Key Features                                                                                       | Use Cases                                                                                                             |
|--------------------------|----------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------|
| `dig`                    | Versatile DNS lookup tool that supports various query types (A, MX, NS, TXT, etc.) with detailed output. | Manual DNS queries, zone transfers (if allowed), troubleshooting DNS issues, and deep DNS analysis.                   |
| `nslookup`               | Basic DNS lookup tool, good for quick queries (A, AAAA, MX).                                        | Fast checks of domain resolution and mail server records.                                                             |
| `host`                   | Streamlined command-line DNS tool with concise results.                                             | Quick lookups for A, AAAA, MX, and CNAME records.                                                                     |
| `dnsenum`                | Automated enumeration with support for dictionary-based subdomain brute-forcing and zone transfers. | Discovering subdomains and mapping DNS infrastructure.                                                               |
| `fierce`                 | Recursive DNS recon tool with wildcard detection and subdomain discovery.                           | DNS reconnaissance and identifying hidden or wildcard subdomains.                                                    |
| `dnsrecon`               | Combines multiple recon techniques (brute force, zone transfers, cache snooping) into one tool.     | Full-scope DNS enumeration with optional output formats for reports or automation.                                   |
| `theHarvester`           | OSINT tool that pulls data like emails and DNS records from search engines and public sources.      | Gathering emails, names, and hostnames associated with a domain during recon.                                        |
| Online DNS Tools         | Browser-based interfaces like MXToolbox, DNSDumpster, etc.                                          | Easy DNS queries without terminal; good for domain availability checks or quick lookups when on a restricted system. |
