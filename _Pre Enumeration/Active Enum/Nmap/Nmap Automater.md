- - -
#### Find Top Open Ports : 

```sh
nmapAutomator.sh --host $IP --type Port --output /tmp/
```

#### Run a Script Scan on found Ports  : 

```sh
nmapAutomator.sh --host $IP --type Script --output /tmp/
```

#### Run A Full range scan and script scan : 

```sh
nmapAutomator.sh --host $IP --type Full --output /tmp/
```

#### Run a UDP Scan : 

```sh
sudo nmapAutomator.sh --host $IP --type UDP --output /tmp/
```

#### Run a vulnerability scan on all open ports : 

```sh
sudo nmapAutomator.sh --host $IP --type Vulns --output /tmp/
```


