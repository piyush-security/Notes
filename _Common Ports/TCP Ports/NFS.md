- - -
- [ ]  **NFS** stands for "**Network File System**" and allows a system to share directories and files with others over a network.
- [ ] By using NFS, users and programs can access files on remote systems almost as if they were local files.
- [ ] It does this by mounting all, or a portion of a file system on a server.
- [ ] The portion of the file system that is mounted can be accessed by clients with whatever privileges are assigned to each file.
- - -
### Show all mounts :

```sh
showmount -e $IP
```

```sh
showmount -a $IP
```

```sh
nmap -sV --script=nfs-showmount $IP
```


### Mount a NFS share :

```sh
```mount $IP:/vol/share /mnt/nfs
```

```sh
mount -t nfs $IP:/vol/share /tmp/mounted
```

```sh
mount -t nfs 10.10.137.228:/home /tmp/mountme -nolock
```


#### Demo :

```sh
root@Offsec:~# mkdir home
root@Offsec:~# sudo mount -o nolock $IP:/home ~/home/
root@Offsec:~# cd home/ && ls
```

