- - -
### With Cewl : 
<br>**<u>Basic Usage</u>** : 
```sh
cewl $URL -m 5  -w  $PWD/cewl.txt 2>/dev/null
cewl $URL -m 5  -d 4  -w  $PWD/cewl.txt 2>/dev/null
```

**<u>Retrieval of Emails from the website :</u>**  
```sh
cewl https://digi.ninja/contact.php -e -n
```

**<u>Create wordlists with numbers also</u>** : 
```sh
cewl http://testphp.vulnweb.com/artists.php --with-numbers
```

**<u>Lowercase all the words in the wordlist</u>** : 
```sh
cewl http://<target_ip>/   --lowercase
```
<br>

### With Cupp : 

**<u>Installation</u>** : 
```sh
git clone https://github.com/Mebus/cupp.git
cd cupp
```

**<u>Basic Usage</u>** : 
```sh
./cupp.py
./cupp.py -w raj.txt
```

**<u>Downlaoding dictionaries</u>** : 
```sh
./cupp.py –l
cd dictionaries
cd hindi
gzip -d hindu-names.gz
cat hindu-names
```

**<u>Downloading  Default Usernames and Passwords</u>** : 
```sh
./cupp.py –a
ls
cat alectodb-passwords.txt
```
<br>

### With Crunch : 
Create you massive personal Dictionary

**<u>Basic Usage</u>** : 
```sh
crunch <min-Chars> <max-Chars> <String> -o /tmp/wordlist.txt
```

```
crunch 5 10 piyush -o /tmp/wordlist.txt
```




- - -




