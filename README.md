# writeup-HTB
#main info:
#machine: Fawn
#Link: https://app.hackthebox.com/machines/Fawn

#tool:
-NMAP
-NetCat
-Ping 

#procces:
#get ip from HTB (10.129.210.233). easy, nmap:

-nmap -sV 10.129.210.233

#result:

Note: Host seems down. If it is really up, but blocking our ping probes, try -Pn
Nmap done: 1 IP address (0 hosts up) scanned in 3.44 seconds

#"Note: Host seems down"? Interesting... Well, try again

-nmap -Pn 10.129.210.233 

#result:
PORT   STATE SERVICE
21/tcp open  ftp
port 21? ok, NetCat
-nc 10.129.210.233 21
421 Timeout.  

#. . . Bad. Try again:

-ftp 10.129.210.233

#result: 

Connected to 10.129.210.233.
220 (vsFTPd 3.0.3)
Name (10.129.210.233:kali):

#dont like password :(
#well, password = nothing, login = anonymous
#time to get flag:
-get flag.txt
