
Nothing on the nmap scan ??? 
But you found a cool and strange sequence of numbers ???
Lets try Port knocking ! ! !  

![Imgur](https://i.imgur.com/q0yDD3K.png)

When you "**knock**" on a port you are really just sending TCP-packets with SYN-flag to that port. The closed port will then respond with a ACK/RST. This basically means that the host has received the TCP-packet and - it ACKnolwdge it, but responds with a Reset (RST) flag.

- **RST** just means that the port is closed.

> [! NOTE ] 
>  After knocking the port urgently run a full port scan.

### Old School Style : 

```sh
  nc $IP port
```


### With Bash Script : 

```sh

for x in 4000 5000 6000; do #change the range with your

nmap -Pn --host-timeout 201 --max-retries 0 -p $x $IP;

done

ssh User@$IP -p <port> #or you can use ‘nc -nv $IP 22’

```

### Only With Knock-d : 

```sh
knock -v 10.10.44.7 42 1337 10420 6969, 63000
```


### With "Knock" && "Rustscan" Command : 

```sh
knock 10.10.29.172 7864 8273 9241 12007 60753 && sleep 1 && rustscan -a 10.10.29.172 -b 65535
```


###  With Bash One-Liner : 

```sh
for x in 4000 5000 6000; do nmap -Pn --host_timeout 201 --max-retries 0 -p $x server_ip_address; done
```


