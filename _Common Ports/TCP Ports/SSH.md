- - -
## Enumeration : 

##### With Nmap : 
```sh
nmap -sV --script="ssh* and note brute" -p22 $IP -oN ssh_script_scan.nmap
```

##### OpenSSH 2.3 < 7.7 - Username Enumeration : 
Exploit Link : https://www.exploit-db.com/exploits/45233

```sh
python 45233.py --port 22 --userList ssh_list.txt --outputFile ssh_enum_results.txt 10.10.10.55
```

- - -
## Access : 

**<u>Simple Style</u>** : 
```sh
ssh <user name>@$IP
```

**<u>With Private Key</u>** : 
```sh
ssh –i key <user name>@$IP
```

> ! [Note]
> Never use **id_rsa** key without giving the ‘<mark style="background: #FF5582A6;">chmod 600 id_rsa</mark>’ permission to it because then it will not work correctly.

- - -


