---
title: "Project Structure Scripts"
description: "Shell scripts for setting up CTF and Red Team project directories"
weight: 2
---
---
Use the following scripts to quickly create standardized directories for your pentesting or red team engagements. It helps keep things clean, organized, and consistent.


## 🚩 CTF Boxes Project Structure

```bash
#!/bin/bash
# Simple project structure

read -p "Enter Project Name: " PROJECT
BASE="$PROJECT"

mkdir -p "$BASE/evidence/credentials"
mkdir -p "$BASE/evidence/data"
mkdir -p "$BASE/evidence/screenshots"
mkdir -p "$BASE/logs"
mkdir -p "$BASE/scans"
mkdir -p "$BASE/scope"
mkdir -p "$BASE/tools"

echo "Project structure for '$PROJECT' created!"
```

