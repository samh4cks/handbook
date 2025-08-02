---
title: Oracle TNS (1522)
type: handbook
weight: 15
---
---

### Cheat sheet 


### NSE Scripts

`find / -type f -name oracle* 2>/dev/null | grep scripts`

```/usr/share/nmap/scripts/oracle-tns-version.nse
/usr/share/nmap/scripts/oracle-sid-brute.nse
```

**Oracle TNS (Transparent Network Substrate)** is Oracle's networking protocol used to connect clients to Oracle databases. It communicates over TCP port 1521, and the component that listens is called the Oracle Net Listener.

```
wget https://download.oracle.com/otn_software/linux/instantclient/214000/instantclient-basic-linux.x64-21.4.0.0.0dbru.zip
wget https://download.oracle.com/otn_software/linux/instantclient/214000/instantclient-sqlplus-linux.x64-21.4.0.0.0dbru.zip
sudo mkdir -p /opt/oracle
sudo unzip -d /opt/oracle instantclient-basic-linux.x64-21.4.0.0.0dbru.zip
sudo unzip -d /opt/oracle instantclient-sqlplus-linux.x64-21.4.0.0.0dbru.zip
export LD_LIBRARY_PATH=/opt/oracle/instantclient_21_4:$LD_LIBRARY_PATH
export PATH=$LD_LIBRARY_PATH:$PATH
source ~/.bashrc
cd ~
git clone https://github.com/quentinhardy/odat.git
cd odat/
pip install python-libnmap
git submodule init
git submodule update
pip3 install cx_Oracle
sudo apt-get install python3-scapy -y
sudo pip3 install colorlog termcolor passlib python-libnmap
sudo apt-get install build-essential libgmp-dev -y
pip3 install pycryptodome
```


| Command                                  | Description             |
|------------------------------------------|-------------------------|
| `./odat.py all -s <target>`              | Run all ODAT tests      |
| `sqlplus scott/tiger@<target>/XE`        | Login using SQLPlus CLI |

| Command                                        | Description                        |
|------------------------------------------------|------------------------------------|
| `SELECT banner FROM v$version;`                | Shows Oracle version & patch info  |
| `SELECT * FROM global_name;`                   | Shows global DB name               |
| `SELECT instance_name FROM v$instance;`        | Shows instance name                |
| `SELECT name FROM v$database;`                 | Displays DB name                   |

| Command                                                  | Description                              |
|----------------------------------------------------------|------------------------------------------|
| `SELECT * FROM all_users;`                               | List all DB users                        |
| `SELECT * FROM dba_users;`                               | Detailed user info (if permitted)        |
| `SELECT username, account_status FROM dba_users;`        | Show user accounts and status            |
| `SELECT * FROM session_privs;`                           | List current session privileges          |
| `SELECT * FROM user_role_privs;`                         | Roles assigned to the current user       |
| `SELECT * FROM dba_roles;`                               | List all DB roles (if accessible)        |

| Command                                                    | Description                   |
|------------------------------------------------------------|-------------------------------|
| `SELECT table_name FROM all_tables;`                       | List all accessible tables    |
| `SELECT table_name FROM user_tables;`                      | List user-owned tables        |
| `DESC <table_name>;`                                       | Describe table structure      |
| `SELECT * FROM <table_name> WHERE ROWNUM <= 10;`           | Show first 10 rows of a table |
