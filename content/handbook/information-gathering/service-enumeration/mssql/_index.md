---
title: MSSQL (1433)
type: handbook
weight: 14
---
---

### Cheat sheet 



### NSE Scripts

`find / -type f -name mssql* 2>/dev/null | grep scripts`

```/usr/share/nmap/scripts/ms-sql-info.nse  
/usr/share/nmap/scripts/ms-sql-brute.nse  
/usr/share/nmap/scripts/ms-sql-empty-password.nse  
/usr/share/nmap/scripts/ms-sql-xp-cmdshell.nse  
/usr/share/nmap/scripts/ms-sql-config.nse  
/usr/share/nmap/scripts/ms-sql-query.nse  
/usr/share/nmap/scripts/ms-sql-tables.nse  
/usr/share/nmap/scripts/ms-sql-users.nse
```

**Microsoft SQL Server (MSSQL)** is Microsoft's relational database engine. It communicates over TCP 1433.
 
If SQL authentication is enabled and misconfigured, it can be a powerful entry point for lateral movement or privilege escalation.
MSSQL supports:
• SQL auth (user/pass)

• Windows auth (Kerberos/NTLM)<br>
• Remote command execution via xp_cmdshell<br>