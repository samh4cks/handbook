---
title: DNS & Subdomains
type: handbook
weight: 2
---
---

### DNS

**DNS** is like the phonebook of the internet. When you type a domain name like example.com into your browser, DNS translates that into an IP address (like 93.184.216.34) so your computer knows where to connect. It's a distributed system that handles queries for various types of records, like:

A record → maps a domain to an IP address

MX record → points to the mail server for that domain

NS record → shows the authoritative name servers

TXT record → holds miscellaneous text (SPF, verification tokens, etc.)

CNAME → creates aliases for domains

### Subdomain

Subdomains are subdivisions of a main domain. Think of them as branches or folders. For example:

* www.example.com
* mail.example.com
* admin.example.com

These are all subdomains of example.com. Each can point to a different server, host a different app, or run a different service. From a security perspective, subdomains matter because:

They can reveal infrastructure (e.g., dev-api.example.com).

Forgotten or unprotected subdomains can be vulnerable to takeover.

Subdomain enumeration helps attackers map out a broader attack surface.