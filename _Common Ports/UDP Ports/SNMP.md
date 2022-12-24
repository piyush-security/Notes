- - -
- Default Port : 161, 162, 10161, 10162 ( udp )
SNMP - Simple Network Management Protocol is a protocol used to monitor different devices in the network (like routers, switches, printers, IoTs...).
- - -
## Enumeration : <br>

###### Useful : 
- [Hacktricks](https://book.hacktricks.xyz/network-services-pentesting/pentesting-snmp)
- [refabr1k.gitbook.io](https://refabr1k.gitbook.io/oscp/info-gathering/snmp)
<br><br>
#####  First thing first you need to install : 

```sh
 sudo apt install snmp-mibs-downloader
```

```sh
nano /etc/snmp/snmp.conf         #[ and comment out the “mibs” line ]
```
<br>

##### SNMP Community Strings : 

``/usr/share/metasploit-framework/data/wordlists/snmp_default_pass.txt``
<br><br>

##### With SnmpCheck : 
First we have to check for public channels : 

```sh
 snmp-check $IP -c public
```
<br>

##### With SnmpWalk || SnmpBulkWalk || SnmpEnum : 

```sh
snmpwalk -c public -v2c $IP 
snmpbulkwalk -Cr1000 -c public -v2c $IP . > snmpwalk.1	  #[Best as per ippsec]
snmpenum $IP public linux.txt
```
<br>

##### For SNMP v3 : 

```sh
 wget https://raw.githubusercontent.com/raesene/TestingScripts/master/snmpv3enum.rb; ./snmpv3enum.rb
```
<br>

#### With OneSixtyOne : 

```sh
./onesixtyone -c /usr/share/seclists/Discovery/SNMP/common-snmp-community-strings.txt $IP

./onesixtyone -c /opt/seclists/Discovery/SNMP/common-snmp-community-strings-onesixtyone.txt $IP
```
<br>

##### With Nmap : 

```sh
nmap -sU -p161 --script "snmp-*" $IP
```
<br>

#### Too much Useful Data : 

This is clalled "The SNMP MIB Trees".

```text
1.3.6.1.2.1.25.1.6.0                                - System Processes
1.3.6.1.2.1.25.4.2.1.2 			                    - Running Programs
1.3.6.1.2.1.25.4.2.1.4 			                    - Processes Path
1.3.6.1.2.1.25.2.3.1.4 			                    - Storage Units
1.3.6.1.2.1.25.6.3.1.2 			                    - Software Name
1.3.6.1.4.1.77.1.2.25 			                    - User Accounts
1.3.6.1.2.1.6.13.1.3 			                    - TCP Local Ports
```

But how to use the above data ?? Don't worry !! :-

```sh
# enumerate windows users
snmpwalk -c public -v1 $ip 1.3.6.1.4.1.77.1.2.25 

# enumerates running processes
snmpwalk -c public -v1 $ip 1.3.6.1.2.1.25.4.2.1.2 
```
<br>

#### With Braa ( A Mass SNMP Scanner) :

It's syntax is  : `braa [Community-string]@[IP of SNMP server]:[iso id]`

```sh
braa public@192.168.1.215:.1.3.6.*
```
<br>

- - -

