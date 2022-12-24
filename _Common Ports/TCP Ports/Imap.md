- - -
**Default Ports - <mark style="background: #FFB8EBA6;">143, 993</mark>.**
IMAP allows you to **access your email messages wherever you are**; much of the time, it is accessed via the Internet. Basically, email **messages are stored on servers**.
- - -

## Enumeration : 

#### With Nmap : 

```sh
nmap --script=imap-* $IP
```

- - -
### Connection Demo : 

```sh
root@Offsec:~% telnet 148.32.42.5 143   

ME -> LOGIN piyush password123
1 OK Logged in  

ME -> LIST "" "*"  
* LIST (\HasNoChildren) "/" INBOX  
2 OK List completed (0.000 + 0.000 secs).  

ME -> EXAMINE INBOX  

ME -> 4 LOGOUT  
* BYE Logging out    
Connection closed by foreign host.  
```

