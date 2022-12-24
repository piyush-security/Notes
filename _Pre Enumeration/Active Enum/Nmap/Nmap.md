- - -
## Nmap :  

```sh  
sudo nmap 10.11.0.128 -p- -sV -vv --open --reason  
```

```sh 
nmap -sV -sC -p- -T4 $IP --open  
```

```sh  
nmap -A -T4 -p- $IP  
```

```sh
nmap -p 1-65535 -sV -sS -A -T4 $IP/24 -oN nmap.txt  
```

```sh
nmap -sV -sU -T4 -A -v $IP/24  
```

```sh
nmap --script=vuln* $IP  
```

```sh  
nmap -sC -sV -O -oA nmap/initial $IP  
```

#### Initial Scan : 
```sh
nmap -sC -sV -O -p- -oA nmap/full $IP 												
```

#### Full Scan : 
```sh  
nmap -sC -sV -O -p- -oA nmap/full $IP												
```

#### TCP Deep_One : 
```sh
nmap -v -p- -sT -T4 -sV  $IP 														 
  ```

#### Be Quick : 
```sh
nmap --top-ports=20 192.168.29.0-254  -Pn
```

