---
title: POP3 (110,995)
type: handbook
weight: 6
---
---

### Cheat sheet

| Command                                                                                                       | Description                                  |
|---------------------------------------------------------------------------------------------------------------|----------------------------------------------|
| `sudo nmap -sV -p110,995 <target>`                                                                            | Detect POP3/POP3S services and versions      |
| `telnet <target> 110`                                                                                         | Manually connect to POP3 over plaintext      |
| `nc <target> 110`                                                                                             | Netcat to interact with POP3 service         |
| `openssl s_client -connect <target>:995`                                                                      | Connect to POP3 over SSL (port 995)          |
| `openssl s_client -starttls pop3 -connect <target>:110`                                                       | Upgrade plaintext to TLS via STARTTLS        |
| `swaks --to test@example.com --server <target> --auth-user <user> --auth-password <pass>`                     | Test POP3 login capability                   |
| `curl --user user:pass pop3://<target>/ -k`                                                                   | Use curl to test POP3 connection and creds   |

### NSE Scripts 

`find / -type f -name pop3* 2>/dev/null | grep scripts`

```/usr/share/nmap/scripts/pop3-capabilities.nse  
/usr/share/nmap/scripts/pop3-brute.nse
```

**POP3 (Post Office Protocol v3)** is used by email clients to retrieve messages from a mail server. Unlike IMAP, POP3 usually downloads and deletes mail from the server 
after retrieval.

• Port 110: Plaintext POP3 (with optional STARTTLS)<br>
• Port 995: POP3S (POP3 over SSL)

| Command        | Description                                               |
|----------------|-----------------------------------------------------------|
| `USER username`| Identifies the user                                       |
| `PASS password`| Authenticates the user using the provided password        |
| `STAT`         | Requests the number of saved emails from the server       |
| `LIST`         | Requests the number and size of all emails                |
| `RETR id`      | Retrieves the email with the specified ID                 |
| `DELE id`      | Deletes the email with the specified ID                   |
| `CAPA`         | Displays server capabilities                              |
| `RSET`         | Resets the session state (undeletes marked emails)        |
| `QUIT`         | Closes the connection with the POP3 server                |

