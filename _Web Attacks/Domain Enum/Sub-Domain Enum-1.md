- - -
## Sumrecon : 

👏 👏 <u>**<mark style="background: #FFB86CA6;">Automated Subdoamin Enumerator for real life pentest</mark>**</u> : 👏 👏 
[https://github.com/Gr1mmie/sumrecon](https://github.com/Gr1mmie/sumrecon)

- - -
## AssetFinder :

#### <u>Intallation</u>

- [ ] visit here [https://github.com/tomnomnom/assetfinder](https://github.com/tomnomnom/assetfinder)
- [ ] And go to releases >>> download the binary.

#### <u>Usage</u>

```sh
assetfinder testla.com
``` 

- - -
## Amass :

```sh
amass enum -d tesla.com
```

- - -

## HTTPROBE : 
( it check for alive/responding subdomains )

#### <u>Intallation</u>

- [ ] visit here [https://github.com/tomnomnom/httprobe](https://github.com/tomnomnom/httprobe)
- [ ] And go to releases >>> download the binary.


#### <u>Usage</u>

```sh
cat subdomains.txt | httprobe
```

( only search for **https** )
```sh
cat subdomains.txt | httprobe -s -p https:443 
```

**Output** All Alive Domains 
```sh
cat subdomains.txt | sort -u | httprobe -s -p https:443 | sed ‘s/https\?:\/\///’ | tr -d ‘:443’ >> alive-domains.txt
```
