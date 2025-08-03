---
title: WHOIS
type: handbook
weight: 1
---
---

### Cheat sheet

| Command                                                    | Description                               |
|------------------------------------------------------------|-------------------------------------------|
| `whois example.com`                                        | Basic WHOIS query for a domain            |
| `whois <ip>`                                               | WHOIS lookup for an IP address            |
| `whois -h whois.arin.net <ip>`                             | Force query to ARIN                       |
| `whois -h whois.ripe.net <ip>`                             | Query RIPE (Europe)                       |
| `whois -h whois.apnic.net <ip>`                            | Query APNIC (Asia)                        |
| `whois --verbose example.com`                              | Verbose output                            |
| `whois -H example.com`                                     | Suppress legal disclaimers                |
| `dig +short NS example.com` and `whois <name-server>`      | Look up registrar of specific name server |

**WHOIS** is a widely used query and response protocol designed to access databases that store information about registered internet resources. 

Primarily associated with domain names, WHOIS can also provide details about IP address blocks and autonomous systems. 

Each WHOIS record typically contains the following information:

• Domain Name: The domain name itself (e.g., example.com)<br>
• Registrar: The company where the domain was registered (e.g., GoDaddy, Namecheap)<br>
• Registrant Contact: The person or organization that registered the domain.<br>
• Administrative Contact: The person responsible for managing the domain.<br>
• Technical Contact: The person handling technical issues related to the domain.<br>
• Creation and Expiration Dates: When the domain was registered and when it's set to expire.<br>
• Name Servers: Servers that translate the domain name into an IP address.<br>


