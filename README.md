# Overview:

-machine: Fawn

-OS: Linux

-Difficulty: Very Easy 

-Link: https://app.hackthebox.com/machines/Fawn

# tool / exploit

-Nmap

-NetCat

-ftp 

# Reconnaissance 

**start with Nmap**

'''nmap -sV 10.129.210.23'''

**result**:

Note: Host seems down. If it is really up, but blocking our ping probes, try -Pn
Nmap done: 1 IP address (0 hosts up) scanned in 3.44 seconds

**well... try again**:

<nmap -Pn 10.129.210.233 >

**result**:

PORT   STATE SERVICE
21/tcp open  ftp

**Exploitation:**

**we use port 21:**

-nc 10.129.210.233 21

**result**:

**#421 Timeout.**

**...bad. try again (i googled, how do it)**

-ftp 10.129.210.233

**result**:

Connected to 10.129.210.233.
220 (vsFTPd 3.0.3)
Name (10.129.210.233:kali):

**dont like password :(**
**(after one hand brutforce)**
**result**:

-Login - anonymous

-Password - nothing

**FTP (File Transfer Protocol) is a standard network protocol used to transfer files between a client and a server over a TCP-based network like the internet**

**on ftp server (if he not protect) everyone can connect to database, didn't know a password**

# lession learned: 

**protect a ftp database**
