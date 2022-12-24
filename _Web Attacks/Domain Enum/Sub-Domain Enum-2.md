- - -
## FUZZING Sub-domains:

Best Wordlist : https://wordlists-cdn.assetnote.io/data/manual/best-dns-wordlist.txt 

```sh
ffuf -c -u "https://FUZZ.target.com" -w <path_to_wordlist> -mc 200,301,302,403
```

```sh
ffuf -i -ic -w /opt/seclists/Discovery/DNS/subdomains-top1million-110000.txt -u http://trick.htb -H "Host: preprod-FUZZ.trick.htb" -of csv -o subs
``` 

```sh
gobuster vhost -w /usr/share/seclists/Discovery/DNS/subdomains-top1million-5000.txt -u http://vulnnet.thm
``` 

 ```sh
gobuster dns -d $URL -w /usr/share/seclists/Discovery/DNS/subdomains-top1million-110000.txt
```

```sh
ffuf -w /usr/share/wordlists/SecLists/Discovery/DNS/namelist.txt -H "Host: FUZZ.acmeitsupport.thm" -u http://10.10.166.242
```

```sh
wfuzz -c -f subdomains.txt -w /usr/share/seclists/Discovery/DNS/subdomains-top1million-5000.txt -u "http://cmess.thm/" -H "Host: FUZZ.cmess.thm" --hl 107
```


