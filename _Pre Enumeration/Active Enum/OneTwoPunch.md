- - - 
The idea behind the script to generate a scan of **65,535** ports on the targets. The script use **unicornscan** to scan all ports, and make a list of those ports that are open. The script then take the open ports and pass them to nmap for service detection.
- - - 

Download Link  : - [Here]([https://github.com/superkojiman/onetwopunch/raw/master/onetwopunch.sh](https://github.com/superkojiman/onetwopunch/raw/master/onetwopunch.sh))

✌️ OR ✌️ 

```sh
git clone https://github.com/superkojiman/onetwopunch.git
cd onetwopunch/
```

> [! NOTE ]
> **Create a text file contains of our targets machine**.

```sh
./onetwopunch.sh -t ip-range.txt tcp
```

```sh
./onetwopunch.sh -t ../targets.txt -p tcp -i tun0
```



