- - -
### Show only those protocal which I want : 

```c
dns
http
ftp
ssh
arp
telnet
icmp     
```


#### More Filters : 

```c
Wireshark Filter by IP                            ip.addr == 10.10.50.1
Filter by Destination IP                          ip.dest == 10.10.50.1

Filter by port (TCP)                              tcp.port == 25
Filter by destination port (TCP)                  tcp.dstport == 23

Filter by ip address and port                     ip.addr == 10.10.50.1 and Tcp.port == 25

Filter by URL                                     http.host == “host name”

MAC address filter                                 eth.addr == 00:70:f4:23:18:c4
Host name filter                                   ip.host = hostname

tcp.port == 80
http.request.method == GET
http.request.method == POST

```



