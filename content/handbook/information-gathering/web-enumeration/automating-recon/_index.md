---
title: Automating Recon
type: handbook
weight: 7
---
---

### Cheat sheet

| Option         | Argument | Description                                                     |
|----------------|----------|-----------------------------------------------------------------|
| `-h`, `--help` |          | Show the help message and exit.                                 |
| `--url`        | URL      | Specify the target URL.                                         |
| `--headers`    |          | Retrieve header information for the target URL.                 |
| `--sslinfo`    |          | Get SSL certificate information for the target URL.             |
| `--whois`      |          | Perform a Whois lookup for the target domain.                   |
| `--crawl`      |          | Crawl the target website.                                       |
| `--dns`        |          | Perform DNS enumeration on the target domain.                   |
| `--sub`        |          | Enumerate subdomains for the target domain.                     |
| `--dir`        |          | Search for directories on the target website.                   |
| `--wayback`    |          | Retrieve Wayback URLs for the target.                           |
| `--ps`         |          | Perform a fast port scan on the target.                         |
| `--full`       |          | Perform a full reconnaissance scan on the target.               |

```
git clone https://github.com/thewhiteh4t/FinalRecon.git
cd FinalRecon
pip3 install -r requirements.txt
chmod +x ./finalrecon.py
./finalrecon.py --help
```

**Automating web reconnaissance** tasks can significantly enhance efficiency and accuracy, allowing you to gather information at scale and identify potential vulnerabilities more rapidly.

These frameworks aim to provide a complete suite of tools for web reconnaissance:

• [FinalRecon](https://github.com/thewhiteh4t/FinalRecon): A Python-based reconnaissance tool offering a range of modules for different tasks like SSL certificate checking, Whois information gathering, header analysis, and crawling. Its modular structure enables easy customisation for specific needs.

• [Recon-ng](https://github.com/lanmaster53/recon-ng): A powerful framework written in Python that offers a modular structure with various modules for different reconnaissance tasks. It can perform DNS enumeration, subdomain discovery, port scanning, web crawling, and even exploit known vulnerabilities.

• [theHarvester](https://github.com/laramies/theHarvester): Specifically designed for gathering email addresses, subdomains, hosts, employee names, open ports, and banners from different public sources like search engines, PGP key servers, and the SHODAN database. It is a command-line tool written in Python.

• [SpiderFoot](https://github.com/smicallef/spiderfoot): An open-source intelligence automation tool that integrates with various data sources to collect information about a target, including IP addresses, domain names, email addresses, and social media profiles. It can perform DNS lookups, web crawling, port scanning, and more.

• [OSINT Framework](https://osintframework.com/): A collection of various tools and resources for open-source intelligence gathering. It covers a wide range of information sources, including social media, search engines, public records, and more.
