- - -
- [ ] Cheat-Sheets ⇒ [**PayloadsAllTheThings**](https://github.com/swisskyrepo/PayloadsAllTheThings/tree/master/XSS%20Injection)
- [ ] Cheat-Sheets ⇒ [**SecLists**](https://github.com/danielmiessler/SecLists/tree/master/Fuzzing/XSS)
- [ ] Cheat-Sheets ⇒ [**hackr.io**](https://hackr.io/blog/xss-cheat-sheet)
- [ ] Cheat-Sheets => https://github.com/Aacle/xss_payload

- - -
###  JSShell :

**Automated Exploiter** : [https://github.com/shelld3v/JSshell](https://github.com/shelld3v/JSshell)

- - -

## Fuzzing : 

```sh
wfuzz -c -z file,/usr/share/seclists/Fuzzing/XSS/XSS-Jhaddix.txt --hh 0 "$URL/index.php?id=FUZZ"
```

- - - 
##  Xira and Dalfox : 

This is a **<u>XSS Vulnerability Scanner</u>**.
Link : [https://github.com/xadhrit/xira](https://github.com/xadhrit/xira)

```python
python3 xira.py -u <url>
```

This is also a  **<u>XSS Vulnerability Scanner</u>**.
Link : [https://github.com/hahwul/dalfox](https://github.com/hahwul/dalfox)

```sh
dalfox url http://testphp.vulnweb.com/listproducts.php
```

