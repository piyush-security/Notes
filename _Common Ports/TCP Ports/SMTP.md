- - -
SMTP stands for "Simple Mail Transfer Protocol". It is utilised to handle the sending of emails. In order to support email services, a protocol pair is required, comprising of SMTP and POP/IMAP. Together they allow the user to send outgoing mail and retrieve incoming mail, respectively.
- - -
## Enumeration : 

Useful : [https://refabr1k.gitbook.io/oscp/info-gathering/smtp](https://refabr1k.gitbook.io/oscp/info-gathering/smtp)

##### Banner Grab : 

```sh
nc -nvv $IP 25
telnet $IP  25
```

##### With Nmap : 

```sh
 nmap --script=smtp-commands,smtp-enum-users,smtp-vuln-cve2010-4344,smtp-vuln-cve2011-1720,smtp-vuln-cve2011-1764 -p 25 $IP
```

##### User Enumeration : 

```sh
smtp-user-enum -M VRFY -U /usr/share/wordlists/metasploit/unix_users.txt -t $IP

smtp-user-enum -M VRFY -D marvel.local -u raj -t 192.168.1.107
```

```sh
ismtp -h 192.168.1.107:25 -e /root/Desktop/email.txt
```

```sh
telnet $IP$ <port>
VRFY <username>                            #raj@mail.lab.ignite
```

```sh
msf > use auxiliary/scanner/smtp/smtp_enum
```

- - -
#### Demo : 
```sh
pentester@TryHackMe$ telnet MACHINE_IP 25
Trying MACHINE_IP...
Connected to MACHINE_IP.
Escape character is '^]'.
220 bento.localdomain ESMTP Postfix (Ubuntu)

helo telnet
250 bento.localdomain

mail from: 
250 2.1.0 Ok

rcpt to: 
250 2.1.5 Ok

data
354 End data with .
subject: Sending email with Telnet
Hello Frank,
I am just writing to say hi!             

.
250 2.0.0 Ok: queued as C3E7F45F06

quit
221 2.0.0 Bye
Connection closed by foreign host.

```

- - -
#### Brute Forcing : 

```sh
hydra -l root -P /root/SecLists/Passwords/10_million_password_list_top_100.txt $IP telnet
```
 - - -

