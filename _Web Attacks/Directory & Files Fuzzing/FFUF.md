- - -
##### **<u>Fuzz Files</u> :**

```sh
ffuf -u $URL -c -w /opt/seclists/Discovery/Web-Content/raft-large-files.txt -t 100
```

##### **Fuzz Directories:**

```sh
ffuf -u $URL -c -w /opt/seclists/Discovery/Web-Content/raft-large-directories.txt -t 100
```

##### **Fuzz Recursivly:**

```sh
ffuf -recursion -c -e '.htm','.php','.html','.js','.txt','.zip','.bak','.asp','.aspx','.xml','.py','.log','.json','.old' -w /usr/share/dirbuster/wordlists/directory-list-2.3-medium.txt -u http://$IP:8080/FUZZ
```

```sh
ffuf -recursion -mc all -ac -c -e .htm,.shtml,.php,.html,.js,.txt,.zip,.bak,.asp,.aspx,.xml -w /usr/share/dirbuster/wordlists/directory-list-2.3-medium.txt -u https://url.com/FUZZ
```

```sh
ffuf -u http://sitename/FUZZ -w /usr/share/seclists/Discovery/Web-Content/big.txt -recursion -e .bak,.aspx,.html,.php,.txt
```

- - - 
