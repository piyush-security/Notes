- - -
Very complete tool for SSL auditing is testssl.sh, finds BEAST, FREAK, POODLE, heart bleed, etc...
- - -
## Enumeration : 

**<u>Open a connection</u>** :
```sh
openssl s_client -connect $IP:443
```

**<u>Basic SSL ciphers check</u>** : 
```sh
nmap --script ssl-enum-ciphers -p 443 $IP
```

> ! [Note]
>  Look for unsafe ciphers such as **Triple-DES** and **Blowfish**

 - - -
