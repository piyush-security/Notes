
### Listen To ICMP requests : 

```sh
sudo tcpdump -i tun0 icmp
```

```sh
sudo tcpdump ip proto \\icmp -i tun0
```

