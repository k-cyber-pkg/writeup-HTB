# Overview

-machine: Sequel

-OS: Linux

-Diffecly: Very easy

-Link: https://app.hackthebox.com/machines/Sequel

# Use Tool

-Nmap

-

# Reconnaissance 

**get IP from HTB, and start scan port:**

``nmap -Pn -sV -T4 10.129.219.200``

**result:**

Not shown: 999 closed tcp ports (reset)

PORT     STATE SERVICE VERSION

3306/tcp open  mysql?

# Exploitation:

**mysql? very interesting. It my first work with mysql. Well, lets try enter in this port (i googled how do it)**

``mysql -h 10.129.219.200 -u root``

**result:**

ERROR 2026 (HY000): TLS/SSL error: SSL is required, but the server does not support it

**this is bad:(**

**try again**

``nc 10.129.219.200``

**result:**

no port[s] to connect to

**okay, dost work. Again**

`` mysql -h 10.129.219.200 -u root -p ``

**result:**

ERROR 2026 (HY000): TLS/SSL error: SSL is required, but the server does not support it

**okay, after this machine... dont work. Idk what do with this. I read the official write up, but her nothing write about this. Commands, i use:**

``mysql -h 10.129.219.251 -u root``

``mysql -h 10.129.219.200 -u root -p``

``curl 10.129.219.200:3306``

``telnet 10.129.219.200``

**result:**

ERROR 2026 (HY000): TLS/SSL error: SSL is required, but the server does not support it

ERROR 2026 (HY000): TLS/SSL error: SSL is required, but the server does not support it

curl: (1) Received HTTP/0.9 when not allowed

Trying 10.129.219.200...
telnet: Unable to connect to remote host: Connection refused
