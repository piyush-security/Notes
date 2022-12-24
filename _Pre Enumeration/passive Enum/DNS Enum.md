
# Basic commands : **( DNS Enum )** ⏳️

- [ ] **Lookup WHOIS record**
```sh
 whois tryhackme.com
```

- [ ] **Lookup DNS A records**
```sh
 nslookup -type=A tryhackme.com
```

- [ ]  **Lookup DNS MX records at DNS server**
```sh
 nslookup -type=MX tryhackme.com 1.1.1.1
```

- [ ] **Lookup DNS TXT records**

```sh
 nslookup -type=TXT tryhackme.com
```

- [ ] **Lookup DNS A records**

```sh
 dig tryhackme.com A
```

- [ ] **Lookup DNS MX records at DNS server**

```sh
 dig @1.1.1.1 tryhackme.com MX
```

- [ ] **Lookup DNS TXT records**

```sh
 dig tryhackme.com TXT
```
