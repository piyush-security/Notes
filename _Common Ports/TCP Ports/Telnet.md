- - -
- Default Port :- 25
Telnet is an application protocol which allows you, with the use of a telnet client, to connect to and execute commands on a remote machine that's hosting a telnet server.
The telnet client will establish a connection with the server. The client will then become a virtual terminal- allowing you to interact with the remote host.
- - -
## Enumeration :

##### Banner Grab : 
```sh
nc -nvv $IP 25
telnet $IP  25
```

##### User Enum And Demo : 
```sh
pentester@TryHackMe$ telnet MACHINE_IP  
Trying MACHINE_IP...  
Connected to MACHINE_IP.  
Escape character is '^]'.  
Ubuntu 20.04.3 LTS  

bento login: frank  

Password: D2xc9CgD  
  
vrfy msfadmin  
252 2.0.0 msfadmin
```


- - - 
#### Bruteforcing  : 

Finding Password
```sh
hydra -l root -P /root/SecLists/Passwords/10_million_password_list_top_100.txt 192.168.1.101 telnet
```

- - - 
