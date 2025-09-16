---
title: "Lateral Movement"
url: "/handbook/lateral-movement/"
weight: 7
---
---

Lateral movement is how an attacker expands their foothold inside a network after an initial compromise: they move from one machine or account to others to access higher-value systems and data. Here’s the thing — it’s not a single trick but a sequence: compromise a host, collect credentials or tokens (or exploit a service), use built-in remote administration channels (RDP, SMB, SSH, WinRM, remote APIs) or abused service accounts to hop to another system, repeat until the objective is reached. Effective lateral movement chains credential reuse, privilege escalation, and misconfigurations with poor segmentation or weak authentication, while trying to stay quiet by using legitimate tools. Defenders disrupt it by reducing credential exposure (unique passwords, managed service accounts), enforcing least privilege and segmentation, requiring strong/multi-factor auth for remote access, and instrumenting detection for anomalous logins, unusual remote service use, and abnormal process chains.


