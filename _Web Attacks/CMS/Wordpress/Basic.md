- - -
## Wpscan :

<u>Simple</u> :
```sh
wpscan --url https://url.com
```

<u>Randon User-agent</u> :
```sh
wpscan --url $URL --random-agent
```

<u>Enumerate Users Plugins and Themes</u> :  ( <mark style="background: #FFB86CA6;">HTTP</mark> )
```sh
wpscan --url http://IP_ADDR --enumerate u,p,t
```

<u>Enumerate Users Plugins and Themes</u> :  ( <mark style="background: #BBFABBA6;">HTTPS</mark> )
```sh
wpscan --url $URL --enumerate u,p,t --disable-tls-checks
```


- - - 
## Wpscan Bruteforcing : 

**<u>For <mark style="background: #FFB86CA6;">HTTP</mark></u>** : 
```sh
wpscan --url $URL --usernames users --passwords /usr/share/wordlists/rockyou.txt
```

**<u>For <mark style="background: #BBFABBA6;">HTTPS</mark></u>** : 
```sh
wpscan --url $URL --usernames users --passwords /usr/share/wordlists/rockyou.txt --disable-tls-checks
```

- - -
## Nmap : 

```sh
nmap -p 80 -vv --script http-wordpress-enum --script-args type="plugins",search-limit=1500 $IP
```

- - -
### Some vulnerability Scanners : 

**<u>Vulnx</u> :**
```sh
vulnx -u https://example.com/ --cms --dns -d -w -e
```

**<u>cmsmap</u> :**
```python
python3 cmsmap.py https://www.example.com -F
```

**<u>wpseku.py</u> :**
```python
python3 wpseku.py --url https://www.target.com --verbose
```

- - -
