---
title: Certificate Transparency Logs
type: handbook
weight: 6
---
---

### Cheat sheet

| Command | Description |
|---------|-------------|
| `curl -s "https://crt.sh/?q=domain&output=json" \| jq -r '.[].name_value' \| grep dev \| sort -u` | Uses crt.sh to fetch cert logs and extract subdomains. |



**Certificate Transparency (CT) logs** are public, append-only ledgers that record the issuance of SSL/TLS certificates. Whenever a Certificate Authority (CA) issues a new certificate, it must submit it to multiple CT logs. Independent organisations maintain these logs and are open for anyone to inspect.

| Tool     | Key Features                                                                 | Use Cases                                                        | Pros                                              | Cons                                  |
|----------|------------------------------------------------------------------------------|------------------------------------------------------------------|---------------------------------------------------|---------------------------------------|
| crt.sh   | Simple interface, search by domain, shows certificate details including SAN. | Finding subdomains, reviewing certificate history for a domain.  | Free, no login needed, easy to use.               | Limited filtering, no API.            |
| Censys   | Advanced filters, search by cert fields, domains, IPs; includes metadata.    | Deep certificate analysis, asset discovery, attack surface mapping. | Rich data, flexible queries, API access.          | Requires account (free tier available). |
