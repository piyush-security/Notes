- - -
- **Default Port:** **<mark style="background: #FFB86CA6;">21</mark>**
The **File Transfer Protocol (FTP**) is a standard network protocol used for the transfer of computer files between a client and server on a computer network. It is a **plain-text** protocol.
- - -

## Download all files from FTP

```sh
wget -m ftp://anonymous:anonymous@10.10.10.98 
wget -m --no-passive ftp://anonymous:anonymous@10.10.10.98 
```

### Nmap NSE : 

```sh
nmap --script=ftp-anon,ftp-bounce,ftp-libopie,ftp-proftpd-backdoor,ftp-vsftpd-backdoor,ftp-vuln-cve2010-4221,tftp-enum -p 21 $IP
```

```sh
nmap --script=ftp-* -p 21 $IP
```

### Brute forcing : 

```sh
hydra -t 4 -l dale -P /usr/share/wordlists/rockyou.txt -vV 10.10.10.6 ftp
```

- - -
