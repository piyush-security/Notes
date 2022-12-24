- - -
**Default ports:** 110, 995(ssl)
**Post Office Protocol** (**POP**) is a type of computer networking and Internet standard **protocol** that extracts and retrieves email from a remote mail server for access by the host machine.
- - -
### Enumeration : 

By Nmap : 

```sh
nmap --script pop3-capabilities,pop3-ntlm-info -sV -port <PORT> $IP
```

- - -
#### Demo : 

```sh
pentester@TryHackMe$ telnet MACHINE_IP 110  
Trying MACHINE_IP...  
Connected to MACHINE_IP.  
Escape character is '^]'.  
+OK MACHINE_IP Mail Server POP3 Wed, 15 Sep 2021 11:05:34 +0300   
  
USER frank  
+OK frank  
  
PASS D2xc9CgD  
+OK 1 messages (179) octets  
  
STAT  
+OK 1 179  
  
LIST  
+OK 1 messages (179) octets  
1 179  
.  
  
RETR 1  
+OK  
From: Mail Server   
To: Frank   
subject: Sending email with Telnet  
Hello Frank,  
I am just writing to say hi!  
.  
  
QUIT  
+OK MACHINE_IP closing connection  
Connection closed by foreign host.
```


