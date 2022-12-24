- - -
Powerview ⇒ https://github.com/PowerShellMafia/PowerSploit/tree/master/Recon
Cheat-Sheet ⇒ https://gist.github.com/HarmJ0y/184f9822b195c52dd50c379ed3117993
- - -
## Usage : 
Should have powerview cheat-sheet.

Transfer powerview to windows. Then :  

```cmd
cd C:\path\to\Powerview\ 
powershell -ep bypass 
```

Now Just play with it :

```powershell
PS>  . .\PowerView.ps1
PS>  Get-NetDomain    ( Replace this with command you want from cheat-sheet ) 
 
PS>  Get-NetDomainController 
PS>  Get-DomainPolicy 
PS>  (Get-DomainPolicy)."system access" 
PS>  Get-NetUser 
PS>  Get-NetUser | select cn 
PS>  Get-NetUser | select samaccountname 
PS>  Get-UserProperty 
PS>  Get-UserProperty  -Properties samaccountname 
PS>  Get-UserProperty  -Properties logoncount 
PS>  Get-UserProperty  -Properties badpwdcount 
PS>  Get-NetComputer 
PS>  Get-NetComputer -FullData 
PS>  Get-NetGroup 
PS>  Get-NetGroupMember -GroupName “<Group_name>" 
PS>  Invoke-ShareFinder 
PS>  Get-NetGPO 								( Group Policies ) 
PS>  Get-NetGPO | select displayname, whenchanged 
PS>  
```

- - -
