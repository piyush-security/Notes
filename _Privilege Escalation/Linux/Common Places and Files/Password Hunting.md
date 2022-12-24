- - -
## Look For Common Places :

#### Check-Out History :

```sh
history
```

```sh
cat /home/user/.bash_history
```


#### Files containing passwords :

```sh
grep --color=auto -rnw '/' -ie "PASSWORD" --color=always 2> /dev/null
```

```sh
find . -type f -exec grep -i -I "PASSWORD" {} /dev/null \;
```

```sh
cat /etc/security/opasswd
```

```sh
cat /etc/shadow
```

```sh
cat /etc/passwd
```

#### Last edited files : ( set here to 10 minnutes )

```sh
find / -mmin -10 2>/dev/null | grep -Ev "^/proc"
```

#### In memory passwords : 

```sh
strings /dev/mem -n10 | grep -i PASS
```

#### Find sensitive files : 

```sh
locate password | more
```

#### SSH Key :

```sh
find / -name authorized_keys 2> /dev/null
```

```sh
find / -name id_rsa 2> /dev/null
```


### Automated hunting :

- [LinPeas.sh](https://github.com/carlospolop/PEASS-ng) ( Actively Managed By The Author )
- [LinEnum.sh](https://github.com/rebootuser/LinEnum)
- [Linux-Exploit-Suggester.sh](https://github.com/mzet-/linux-exploit-suggester)
- [LinuxprivEscCheacker.py](https://github.com/sleventyeleven/linuxprivchecker)

- - -

