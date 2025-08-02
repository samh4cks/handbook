---
title: Information Gathering
type: handbook
prev: handbook/first-page
next: handbook/information-gathering/leaf
---

Information gathering (also called reconnaissance) is the first and one of the most critical phases in the penetration testing process. 
In this stage, testers systematically collect as much data as possible about the target system, network, or application.

### Enumeration

It’s the process of actively and passively gathering detailed info about a target, going beyond just quick scans to deeply understand its network, services, and structure.

• **Not Just OSINT**: 
Unlike OSINT, which only passively collects public data, enumeration combines both active probing and ongoing research, looping repeatedly to refine your knowledge as new info 
surfaces.

• **Think Like a Treasure Hunter**:
You wouldn’t just start digging randomly for treasure—you’d study maps, prepare tools, and learn the terrain first. Enumeration is similar: map the network and infrastructure carefully 
before launching any attacks.

• **Why Blind Attacks Fail**:
Jumping straight to brute-forcing passwords or noisy attacks is a rookie mistake—it alerts defenders, may get you blacklisted, and often wastes valuable time.

• **Look Beyond the Obvious**:
Focus not only on what you can see (open ports, known services) but also what’s hidden or doesn’t respond. Sometimes the unknown holds the key to deeper access.

##### • Ask These Questions:

1. What can I actually see?
2. Why am I seeing this?
3. What does this tell me about the target?
4. What can I learn from it?
5. What am I NOT seeing?
6. Why is it hidden?
7. What does the absence of info imply?

##### • Core Principles to Remember:

1. There’s always more than meets the eye—consider multiple viewpoints.
2. Distinguish what’s visible from what’s hidden.
3. There are always ways to gather more information—keep exploring.

##### • The Goal:
To discover all possible paths to your target calmly and methodically, not just to “break in” quickly. This strategic groundwork makes penetration testing smarter and far more effective.

![landscape](/handbook/static/information-gathering/enumeration-map.png)

| Layer              | Description                                                                                     | Information Categories                                                                                          |
|--------------------|-------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
| 1. Internet Presence | Identification of internet presence and externally accessible infrastructure.                  | Domains, Subdomains, vHosts, ASN, Netblocks, IP Addresses, Cloud Instances, Security Measures                  |
| 2. Gateway           | Identify the possible security measures to protect the company's external and internal infrastructure. | Firewalls, DMZ, IPS/IDS, EDR, Proxies, NAC, Network Segmentation, VPN, Cloudflare                              |
| 3. Accessible Services | Identify accessible interfaces and services that are hosted externally or internally.          | Service Type, Functionality, Configuration, Port, Version, Interface                                            |
| 4. Processes         | Identify the internal processes, sources, and destinations associated with the services.       | PID, Processed Data, Tasks, Source, Destination                                                                 |
| 5. Privileges        | Identification of the internal permissions and privileges to the accessible services.          | Groups, Users, Permissions, Restrictions, Environment                                                           |
| 6. OS Setup          | Identification of the internal components and systems setup.                                   | OS Type, Patch Level, Network config, OS Environment, Configuration files, Sensitive private files             |
