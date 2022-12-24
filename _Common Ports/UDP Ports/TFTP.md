- - -
**Default Port:** 69/UDP
- - -
### Enumeration : 

##### With Nmap : 

```sh
nmap -n -Pn -sU -p69 -sV --script tftp-enum <IP>
```
<br>

##### Can we download/upload files : 

```sh
auxiliary/admin/tftp/tftp_transfer_util
```

```python
# This is a python script for checking download/upload files. 
import tftpy
client = tftpy.TftpClient(<ip>, <port>)
client.download("filename in server", "/tmp/filename", timeout=5)
client.upload("filename to upload", "/local/path/file", timeout=5)
```
<br>
- - -