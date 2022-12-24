- - -
- Default Port :- 139, 445
👻️ The Server Message Block (SMB) protocol is a network file sharing protocol 
that allows applications on a computer to read and write to files and to request services from server programs in a computer network. 
- - -
## Enumeration : 

##### List All Share : 
```sh
smbclient -L $IP
smbmap -H 192.168.1.40
crackmapexec smb 192.168.1.17 -u '' -p '' --shares
```

##### Connect To Share : 
```sh
smbclient --no-pass //<IP>/<Folder>
```


### With Nmap : 

```sh
nmap --script smb-enum-shares -p139,445 192.168.1.17
```

```sh
nmap --script smb-vuln* -p 445 192.168.1.101
```

```sh
nmap --script smb-enum-domains.nse,smb-enum-groups.nse,smb-enum-processes.nse,smb-enum-sessions.nse,smb-enum-shares.nse,smb-enum-users.nse,smb-ls.nse,smb-mbenum.nse,smb-os-discovery.nse,smb-print-text.nse,smb-psexec.nse,smb-security-mode.nse,smb-server-stats.nse,smb-system-info.nse,smb-vuln-conficker.nse,smb-vuln-cve2009-3103.nse,smb-vuln-ms06-025.nse,smb-vuln-ms07-029.nse,smb-vuln-ms08-067.nse,smb-vuln-ms10-054.nse,smb-vuln-ms10-061.nse,smb-vuln-regsvc-dos.nse -p 139,445 $IP
```

#### With Enum4Linux :

```sh
enum4linux -A -a  $IP -oA enum4linux.txt
```

- - -

