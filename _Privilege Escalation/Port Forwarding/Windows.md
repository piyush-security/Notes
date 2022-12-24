- - - 
Sometimes this is eaziest to run an exploit from kali, but the vulnerable program is listening in the internal port. 
In these cases we need to forward port on our Kali to the internal  port on windows.
We can do this by using a program called plink.exe ( from the makers of PUTTY ).
- - -

```sh
pkill --full smbserver.py
```

enable the ‘PermitRootLogin  Yes’
```sh
vim /etc/ssh/ssh_config
```

```sh
service ssh restart 
```

Now Download and transfer the plink.exe to windows.

```powershell
.\plink.exe root@<our_ip>   -R <remote_port>:127.0.0.1:<port_we _want_to_forwand>

> Y
root password : <your root password>
```

Now press ENTER few times.....Until you get back on your kali prompt.

Now Go and access that port on your Local Host.
<br>

- - -


