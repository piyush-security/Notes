- - -
### Finding Scripts :

```sh 
locate .nse | grep [port name]
```

```sh
ls -la /usr/share/nmap/scripts/ | grep -e '[ port name ]'
```


#### What These Script Do ??

```sh 
nmap --script-help [script name]
```


#### Vulnerability Scanning : 

```sh 
nmap --script vuln $IP
```

```sh 
nmap --script vuln $IP
```

%%  A-Z Scripts on target , may take an hours %%
```sh 
nmap -p 80 --script=all $IP
```

%% use all HTTP Scripts %%
```sh 
nmap -p 80 --script=http*vuln* $IP 
```

```sh 
nmap -p 80 --script=http*vuln* $IP 
```

%% entire network for a directory traversal vulnerability %%
```sh 
nmap -p 80 --script=http-vuln-cve2010-2861 $IP/24
```

