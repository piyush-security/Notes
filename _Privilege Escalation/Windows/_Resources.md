- - -
Note : Every PrivEsc File is transfered using **SMB**.
- - -
## Tools for windows PrivEsc Enumeration :

**PowerUp** : `hunts for specfic Privilege-Esclation misconfiguratiions. wirtten in powershell. can be run on Powershell only.`

**SharpUp** : `similar to PowerUp, written in C#, It is used when powershell is not available. can be run on CMD/Powershell also.`

### To run PowerUp :

```powershell
powershell -exec bypass
. .\PowerUp.ps1
Invoke-AllChecks
```
<br>

- - -

##### WADComs : 
[https://wadcoms.github.io/](https://wadcoms.github.io/) ( **usefull for AV bypass** )

##### LOLBAS 
[https://lolbas-project.github.io/](https://lolbas-project.github.io/)
<br>

- - - 
### To run SharpUp : 

```powershell
.\SharpUp.exe
```
<br>

- - - 

**Seatbelt** :` It is an enumeration tool. It contains numeber of enumeration checks. It Doen not hunt for common PrivEsc misconfiguration,
`But provides related information for further investigation. “all” option gives huge amount of data, So just output it to any other file and read it in code editor.`

```powershell
.\Seatbelt.exe                                      # helpmenu
.\Seatbelt.exe all
```

<br>

- - -

**winPEAS** : `This is a very powerful tool that not only actively hunts for PrivEsc misconfurations but also highlights them in red for reader.`

In all the above tools this is most maintained.

```powershell
reg add HKCU\Console /v VirtualTerminalLevel /t REG_DWORD /d 1
```

Now open a new CMD , the above command activated colours for new CMD.

```powershell
.\winPEAS.exe
```
 
<br>

-------

**Kernal attack** : `Use Windows-Exploit-Suggester.

`Find Exploits on : Google, ExploitDB, GitHub.`

or Find on : 
[https://github.com/SecWiki/windows-kernal-exploits](https://github.com/SecWiki/windows-kernal-exploits)
[https://github.com/rasta-mouse/Watson](https://github.com/rasta-mouse/Watson)
<br>

- - - 

