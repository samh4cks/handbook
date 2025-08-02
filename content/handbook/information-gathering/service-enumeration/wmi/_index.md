---
title: WMI (Over RPC) - 135
type: handbook
weight: 19
---

---

### Cheat sheet 

| Command                                                                                                    | Description                                     |
|------------------------------------------------------------------------------------------------------------|-------------------------------------------------|
| `wmic /node:<target> /user:<user> /password:<pass> process list`                                           | List running processes on remote system         |
| `wmic /node:<target> /user:<user> /password:<pass> process call create "<cmd>"`                            | Remotely execute a command                      |
| `wmiexec.py <user>:<pass>@<target>`                                                                        | Interactive shell using Impacket's WMI Exec     |
| `crackmapexec wmi <target> -u <user> -p <pass> --exec-method smbexec`                                      | Execute command via WMI using CrackMapExec      |
| `powershell "Get-WmiObject -Class Win32_OperatingSystem -ComputerName <target>"`                           | Query basic system info using PowerShell + WMI  |

**WMI** is a built-in Windows framework for querying and managing system information and performing administrative tasks.

It works locally and remotely, over DCOM (RPC-based), and allows process execution, service management, user enumeration, and more.

• Protocol: DCOM/RPC

• Ports:

   ▪ 135/TCP (RPC endpoint)<br>
   ▪ Dynamic RPC: 49152–65535 (usually negotiated)<br>

• Auth: NTLM, Kerberos

• Access Requirements:

   ▪ User must be part of Administrators or Distributed COM Users<br>
   ▪ Firewall must allow remote WMI/DCOM<br>


