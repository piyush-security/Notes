- - -

- - -
## Enumeration : 

Best Resources :
[https://medium.com/](https://medium.com/@minimalist.ascent/pentesting-ldap-servers-25577bde675b)
[Hacktricks](https://book.hacktricks.xyz/network-services-pentesting/pentesting-ldap)
https://www.n00py.io/2020/02/exploiting-ldap-server-null-bind/

#### By Jxplorer : 

This is **GUI** tool used for **browsering LDAP**. 
```markdown
# jxplorer

• click on ‘file’
• click on ‘connect’
• enter your target details
```


#### By LDapSearch : 

```sh
ldapsearch -h $IP -p 389 -x -b "dc=mywebsite,dc=com"
```

**<u>Simple Authentication (Anonymous Bind)</u>** : 
```sh
ldapsearch -H ldap://athos.host -x -LLL
```


- - -