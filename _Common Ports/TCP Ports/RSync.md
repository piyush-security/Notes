- - -
**Default port:** 873
rsync is a utility for efficiently transferring and synchronizing files between a computer and an external hard drive and across networked computers by comparing the modification timesand sizes of files. It is commonly found on Unix-like operating systems. The rsync algorithm is a type of delta encoding, and is used for minimizing network usage.
- - - 
### Enumeration : 

Useful : [hacktricks.xyz](https://book.hacktricks.xyz/network-services-pentesting/873-pentesting-rsync)
[linux-hacking-case-studies-part-1-rsync/](https://www.netspi.com/blog/technical/network-penetration-testing/linux-hacking-case-studies-part-1-rsync/)

##### With Nmap : 
```sh
nmap --script rsync-list-modules.nse $IP -p <port>
```


##### With Rsync : 

List Directory : 
```sh
rsync 10.10.10.10::
```

List Sub Directory : 
```sh
rsync 127.0.0.1::files
```

List Directories & Files Recursively : 
```sh
rsync -r 127.0.0.1::files/tmp/
```

Downloading Files & Folders : 
```sh
rsync 127.0.0.1::files/tmp/test.txt .
rsync -r 127.0.0.1::files/tmp
```

Uploading Files & Folders : 
```sh
rsync ./file.txt 127.0.0.1::files/test
rsync -r ./folder 127.0.0.1:files/test
```


