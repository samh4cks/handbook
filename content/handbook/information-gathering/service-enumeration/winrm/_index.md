---
title: WinRM (5985,5986)
type: handbook
weight: 18
---
---

### Cheat sheet 

| Command                                                                                      | Description                                          |
|----------------------------------------------------------------------------------------------|------------------------------------------------------|
| `nmap -p5985,5986 -sV <target>`                                                              | Detect WinRM service and version                     |
| `nmap --script http-winrm-enum <target>`                                                     | Enumerate WinRM (if script is available)             |
| `evil-winrm -i <target> -u <user> -p <pass>`                                                 | Get an interactive PowerShell shell via WinRM        |
| `evil-winrm -i <target> -u <user> -H <NTLM hash>`                                            | Authenticate using NTLM hash (Pass-the-Hash)         |
| `crackmapexec winrm <target> -u <user> -p <pass>`                                            | Check if credentials are valid over WinRM            |
| `crackmapexec winrm <target> -u <user> -H <hash>`                                            | Check NTLM hash validity over WinRM                  |
| `powershell -NoP -NonI -W Hidden -Exec Bypass -Command "..."`                                | Execute PowerShell code in a stealthy session        |
| `msfconsole → use auxiliary/scanner/winrm/winrm_login`                                       | Use Metasploit to bruteforce WinRM login             |

**WinRM (Windows Remote Management)** is a Microsoft protocol based on WS-Management.
 It enables remote execution and management of Windows systems via SOAP over HTTP/HTTPS.

• Ports:

   ▪ 5985 → HTTP (unencrypted by default)<br>
   ▪ 5986 → HTTPS (encrypted)<br>

• Usage:
 
   ▪ Remote PowerShell access<br>
   ▪ Automation/configuration via Ansible, WinRM clients<br>
   ▪ Admin tasks from domain controllers<br>

• Auth: NTLM, Kerberos, CredSSP
• Default: Disabled on workstations, enabled on servers in domain

