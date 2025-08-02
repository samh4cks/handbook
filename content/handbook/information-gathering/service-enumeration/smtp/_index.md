---
title: SMTP (25,465,587)
type: handbook
weight: 3
---
---

### Cheat sheet 

| Command                                                                                                                        | Description                          |
|--------------------------------------------------------------------------------------------------------------------------------|--------------------------------------|
| `sudo nmap -sV -p25,465,587 <target>`                                                                                          | Detect SMTP services and versions    |
| `nmap --script smtp-commands -p25 <target>`                                                                                    | List supported SMTP commands         |
| `nmap --script smtp-enum-users -p25 --script-args smtp-enum-users.methods={VRFY} <target>`                                     | Attempt user enumeration             |
| `smtp-user-enum -M VRFY -U userlist.txt -t <target> -v -w20`                                                                   | User enumeration                     |
| `telnet <target> 25`                                                                                                           | Manually connect to SMTP (port 25)   |
| `nc <target> 25`                                                                                                               | Netcat for banner grab or testing    |
| `swaks --to test@example.com --from you@you.com --server <target> --data < email.txt`                                          | Send test SMTP payload               |
| `openssl s_client -starttls smtp -connect <target>:587`                                                                        | Test STARTTLS support                |
| `openssl s_client -connect <target>:465`                                                                                       | Test SSL SMTP (SMTPS)                |
| `python3 -m smtpd -n -c DebuggingServer localhost:1025`                                                                        | Run a dummy SMTP server locally      |

### NSE Scripts

`find / -type f -name smtp* 2>/dev/null | grep scripts`

```/usr/share/nmap/scripts/smtp-commands.nse  
/usr/share/nmap/scripts/smtp-enum-users.nse  
/usr/share/nmap/scripts/smtp-open-relay.nse  
/usr/share/nmap/scripts/smtp-strangeport.nse
```

The **Simple Mail Transfer Protocol (SMTP)** is a protocol for sending emails in an IP network. 

It can be used between an email client and an outgoing mail server or between 
two SMTP servers. 

SMTP is often combined with the IMAP or POP3 protocols.

It operates over:

• Port 25: Server-to-server email transmission (plaintext)<br>
• Port 587: Submission with STARTTLS (client to server, secured)<br>
• Port 465: Implicit TLS (SMTPS, deprecated but still used)<br>

|              |   |                        |   |                  |   |                           |   |                     |
|--------------|---|------------------------|---|------------------|---|---------------------------|---|---------------------|
| Client (MUA) | ➞ | Submission Agent (MSA) | ➞ | Open Relay (MTA) | ➞ | Mail Delivery Agent (MDA) | ➞ | Mailbox (POP3/IMAP) |
|              |   |                        |   |                  |   |                           |   |                     |


| Command     | Description                                                                                                  |
|-------------|--------------------------------------------------------------------------------------------------------------|
| `AUTH PLAIN`| AUTH is a service extension used to authenticate the client.                                                 |
| `HELO`      | The client logs in with its computer name and thus starts the session.                                       |
| `MAIL FROM` | The client names the email sender.                                                                           |
| `RCPT TO`   | The client names the email recipient.                                                                        |
| `DATA`      | The client initiates the transmission of the email.                                                          |
| `RSET`      | The client aborts the initiated transmission but keeps the connection between client and server.            |
| `VRFY`      | The client checks if a mailbox is available for message transfer.                                            |
| `EXPN`      | The client also checks if a mailbox is available for messaging with this command.                            |
| `NOOP`      | The client requests a response from the server to prevent disconnection due to time-out.                    |
| `QUIT`      | The client terminates the session.                                                                           |

![SMTP](smtp.png)

• **MUA (Mail User Agent)** – The email client used by the end user to send or read emails (e.g., Outlook, Thunderbird).

• **MSA (Mail Submission Agent)** – Receives mail from the MUA and submits it to the MTA, usually over port 587.

• **MTA (Mail Transfer Agent)** – Transfers emails between servers using SMTP (e.g., Postfix, Exim, Sendmail).

• **MDA (Mail Delivery Agent)** – Takes email from the MTA and delivers it to the recipient’s mailbox (e.g., Dovecot, Procmail).
