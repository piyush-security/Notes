- - -
- Default Port :- <mark style="background: #BBFABBA6;">88</mark>
**Kerberos** is a protocol that is used for network authentication. Different versions are used by Linux and Windows. But if you see a machine with port **88** open you can be fairly certain that it is a **Windows Domain Controller** ( <mark style="background: #FF5582A6;">DC</mark> ).
- - -

If you already have a login to a user of that domain you might be able to escalate that privilege.
Check out: <mark style="background: #D2B3FFA6;">MS14-068</mark>
one Exploit Link : [https://github.com/mubix/pykek](https://github.com/mubix/pykek)

- - -
### Enumeration : 

```sh
nmap -p 88 --script=krb5-enum-users --script-args="krb5-enum-users.realm='DOMAIN.LOCAL'" $IP
```

```python
python kerbrute.py -dc-ip $IP -users /root/htb/kb_users.txt -passwords /root/pass_common_plus.txt -threads 20 -domain DOMAIN -outputfile kb_extracted_passwords.txt
```

```sh
use auxiliary/gather/kerberos_enumusers
```

