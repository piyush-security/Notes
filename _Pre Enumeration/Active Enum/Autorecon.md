
## Basic Commands : 🚨️🚨️🚨️🚨️

```sh 
autorecon -vv $IP
```

```sh
python3 autorecon.py -ct 4 -cs 10 -o ./IP_1 IP_2 IP_3 IP_4
```

```sh
autorecon -t targets.txt
```


### Updates every 5 seconds what is happening **:** ⏰️ 🕰️

```sh
autorecon 192.168.126.133 --heartbeat 5
```


### Append your argument : 🤥️ 🤥️ 🤥️

```sh
autorecon 192.168.126.133 --nmap-append -sS
```


### Creates only Scan Directoy : 💰️ 💰️ 💰️

```sh
autorecon 192.168.154.130 --only-scans-dir
```


###  Combo Of All : 💥️ 💥️ 💥️

```sh
/opt/tools/recon/AutoRecon/autorecon.py --dirbuster.tool ffuf --only-scans-dir 127.0.0.1
```


