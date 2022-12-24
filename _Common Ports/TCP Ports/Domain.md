- - -
- **Default Port - <mark style="background: #FFF3A3A6;">53</mark>** 
The Domain Name Systems (DNS) is the phonebook of the Internet. Humans access information online through domain names, like nytimes.com or espn.com. Web browsers interact through Internet Protocol (IP) addresses. DNS translates domain names to [IP addresses](https://www.cloudflare.com/learning/dns/glossary/what-is-my-ip-address/) so browsers can load Internet resources.
- - -
#### Using Nslook-Up : 

```sh
>>> nslookup
> server $IP
> 127.0.0.1
> $IP
```

- - -
#### Banner Grabbing : 

```sh
nmap -n --script "(default and *dns*) or fcrdns or dns-srv-enum or dns-random-txid or dns-random-srcport" $IP
```

```sh
nmap --script dns-brute --script-args dns-brute.threads=12 '<Domain>'
```

```sh
fierce -dns '<Domain>'
fierce -dns '<Domain>' -dnsserver '<DNS>'
```

```sh
dnsenum --dnsserver '<IP>' --enum '<Domain>'
```

```sh
nslookup -query=mx '<Domain>' -server '<DNS-IP>'                                                                                                                                                         
nslookup -query=ns '<Domain>'  -server '<DNS-IP>'
nslookup -query=any '<Domain>' -server '<DNS-IP>'
```

```sh
dig '<Domain>'
dig '<Domain>' A
dig '<Domain>' AAAA
dig '<Domain>' PTR
dig '<Domain>' NS
dig '<Domain>' MX
```

##### Resolve DNS IP to Domain name.
```sh
dig '@172.16.5.10' -x '172.16.5.10' +nocookie
```


##### Brute force : 
```sh
fierce --domain '<Domain>' --range <Range> --dns-servers '<IP>' --subdomain-file '<wordlist>'
```

##### Brute force with Bash : 
```sh
for name in $(cat /usr/share/seclists/Discovery/DNS/subdomains-top1million-20000.txt); do host $name.sportsfoo.com '172.16.5.10' -W 2; done | grep 'has address'
```

##### Zone Transfer : 
```sh
dig '@<IP>' -t AXFR '<Domain>' +nocookie
```

- - -

