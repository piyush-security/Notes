- - -

##### **<u>Fuzz Directories </u>:**
```sh
wfuzz -c -z file,/opt/seclists/Discovery/Web-Content/raft-large-directories.txt --hc 404 “$URL”
```

##### **<u>Fuzz Files</u> :**
```sh
wfuzz -c -z file,/opt/seclists/Discovery/Web-Content/raft-large-files.txt --hc 404 “$URL”
```

##### **<u>LARGE WORDS</u> :**
```sh
wfuzz -c -z file,/opt/seclists/Discovery/Web-content/raft-large-words.txt --hc 404 “$URL”
```

##### **<u>wfuzz XSS Fuzzing</u>** : 
```sh
wfuzz -c -z file,/usr/share/wordlits/Fuzzing/XSS.txt “$URL”
```

##### **<u>Command Injection</u>** : 
```sh
wfuzz -c -z file,/usr/share/worlists/Fuzzing/command-injection.txt -d “doi=FUZZ” “$URL”
```

##### **<u>html_escape</u>** : 
```sh
wfuzz -c -z file,/usr/share/wordlists/Fuzzing/yeah.txt “$URL”
```

##### **<u>USERS</u> :**
```sh
wfuzz -c- z file,/opt/seclists/Usernames/top-usernames-shortlist.txt --hc 404,403 “$URL”
```

##### **<u>FUZZ SQl-i</u> :**
```sh
wfuzz -c -z file,/usr/share/seclists/Fuzzing/SQLi/quick-SQLi.txt -d "myusername=john&mypassword=FUZZ&Submit=Login” --hc 404 $URL
```



