- - -
Check-List [Link](https://book.hacktricks.xyz/linux-hardening/linux-privilege-escalation-checklist)
- - -

If you are lazy → automatic → use scripts:

```sh
./linpeas.sh -a > /dev/shm/linpeas.txt
```

Or use [https://github.com/liamg/traitor](https://github.com/liamg/traitor) For Low Hanging Fruits.

## I just got a low-priv shell  : 

```python
python -c 'import pty; pty.spawn("/bin/bash")'
```

**OR**

```python
python3 -c 'import pty; pty.spawn("/bin/bash")'

export PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/tmp

export TERM=xterm-256color
alias ll='ls -lsaht --color=auto'

Ctrl + Z [Background Process]

stty raw -echo ; fg ; reset
stty columns 200 rows 200
```

- - -
## **Operating System**

#### Compilation? ( Very Back Burner ) 

```sh 
cat /etc/issue
cat /etc/*-release
uname -a
cat /proc/version
cat /etc/lsb-release                                  # Debian based
cat /etc/redhat-release                               # Redhat based
```

#### What Arch 

```sh
file /bin/bash
```

#### Environmental variables?

```sh
cat /etc/profile
cat /etc/bashrc
cat ~/.bash_profile
cat ~/.bashrc
cat ~/.bash_logout
env
```


#### Is there a printer ? 

```sh
lpstat -a
```

- - -
## **Applications & Services**

#### What services are running ? 

```sh
ps aux | grep -i ‘root’ --color=auto
ps -ef | grep -i ‘root’ --color=auto
top
cat /etc/services
```

#### What applications are installed ? 

```sh
ls -alh /usr/bin/
ls -alh /sbin/
dpkg -l
rpm -qa #red hat
ls -alh /var/cache/apt/archivesO
ls -alh /var/cache/yum/
```

#### Any Conjob ? 

```sh
crontab -l
cat /etc/cron*
ls -al /etc/cron*
cat /etc/crontab
```

#### Start monitoring the system
[ Use pspy ](https://github.com/DominicBreuker/pspy/blob/master/README.md)

```sh
cd /var/tmp/
```

File Transfer → pspy32
File Transfer → pspy64

```sh
chmod 755 pspy32 / pspy64
./pspy<32/64>
```

#### Any plain text usernames and/or passwords ? 

```sh 
grep -i user [filename]
grep -i pass [filename]
```


#### List Every Wirtable FilesOn the System

```sh 
find / -type f -a \( -perm -u+s -o -perm -g+s \) -exec ls -l {} \; 2> /dev/null
```


#### If I can't write , Can I append to a Specific file

```sh
lsattr file.txt
```

#### If you found TMUX use that!!

```sh
cd <tmux_folder>
tmux -S default attach
```

- - -

## **Communications & Networking**

#### What other users & hosts are communicating with the system ? 

```sh
netstat -antup
netstat -tulpn
netstat -antpx
```

#### Is port forwarding possible ? 

```sh 
ssh -[L/R] [local port]:[remote ip]:[remote port] [local user]@[local ip]

ssh -L 8080:127.0.0.1:80 root@192.168.1.7              # Local Port
ssh -R 8080:127.0.0.1:80 root@192.168.1.7              # Remote Port
```

#### Is tunnelling possible ? 

- - -

## Confidential Information & Users : 

#### Know Yourself First 

```sh 
id                                       # note your groups
whoami
cat /etc/passwd | cut -d: -f1
```


#### What Is My Powers ? 

```sh
sudo -l
ls -lsaht /etc/sudoers
```


#### Who Is My Neighbour ? 

```sh
cd /home/ && ls -lsaht
```

#### What sensitive files can be found ? 

```sh
cat /etc/passwd
cat /etc/group
cat /etc/shadow
ls -alh /var/mail/
```


#### Web Configs containing credentials ? 

```sh
cd /var/www/html/ && ls -lsaht``1
```

#### Are there any passwords on Default paths : 

```sh
cat /var/apache2/config.inc
cat /var/lib/mysql/mysql/user.MYD
cat /root/anaconda-ks.cfg
```


#### Can private-key information be found ? 

```sh
cat ~/.ssh/authorized_keys
cat ~/.ssh/identity.pub
cat ~/.ssh/identity
cat ~/.ssh/id_rsa.pub
cat ~/.ssh/id_rsa
cat ~/.ssh/id_dsa.pub
cat ~/.ssh/id_dsa
cat /etc/ssh/ssh_config
cat /etc/ssh/sshd_config
cat /etc/ssh/ssh_host_dsa_key.pub
cat /etc/ssh/ssh_host_dsa_key
cat /etc/ssh/ssh_host_rsa_key.pub
cat /etc/ssh/ssh_host_rsa_key
cat /etc/ssh/ssh_host_key.pub
cat /etc/ssh/ssh_host_key
```

- - -

## **File Systems**

#### Files can be written in /etc/ ?   

```sh
ls -lah /etc/ --color=auto
```

#### What can be found in /var/  ? 

```sh
ls -alh /var/www --color=auto
ls -alh /var/log --color=auto\
ls -alh /var/mail --color=auto
ls -alh /var/spool --color=auto``
```

#### Any files (hidden) on website ? 

```sh
ls -alhR /var/www/ --color=auto
```

Any exotic file system mounts/extended attributes ? 

```sh
mount -l
df -h
```

#### Are there any unmounted file-systems ? 

```sh
cat /etc/fstab
```


#### SUID & GUID : 

[https://gtfobins.github.io/](https://gtfobins.github.io)
Tool Link : [https://github.com/Anon-Exploiter/SUID3NUM](https://github.com/Anon-Exploiter/SUID3NUM)

```sh
find / -perm -u=s -type f 2>/dev/null
find / -perm -g=s -type f 2>/dev/null
```


#### Word-writeable : 

```sh
/var/tmp/
/tmp/
/dev/shm/
```

#### Capabilities : 

```sh
getcap -r / 2>/dev/null
```

## **Preparation & Finding Exploit Code**

#### Various Capabilities?/What languages ? 

```sh
which gcc
which cc
which python
which perl
which wget
which curl
which fetch
which nc
which ncat
which nc.traditional
which socat
```

#### Finding exploit code : 

[http://www.exploit-db.com](http://www.exploit-db.com)
[http://1337day.com](http://1337day.com)
[http://www.securiteam.com](http://www.securiteam.com)
[http://www.securityfocus.com](http://www.securityfocus.com)
[http://www.exploitsearch.net](http://www.exploitsearch.net)
[http://metasploit.com/modules/](http://metasploit.com/modules/)
[http://securityreason.com](http://securityreason.com)
[http://seclists.org/fulldisclosure/](http://seclists.org/fulldisclosure/)
[http://www.google.com/](http://www.google.com/)


#### More information regarding the exploit : 
[http://packetstormsecurity.org/files/cve/[CVE](http://packetstormsecurity.org/files/cve/[CVE)]
[http://cve.mitre.org/cgi-bin/cvename.cgi?name=[CVE](http://cve.mitre.org/cgi-bin/cvename.cgi?name=[CVE)]
[http://www.vulnview.com/cve-details.php?cvename=[CVE](http://www.vulnview.com/cve-details.php?cvename=[CVE)]
[http://www.cvedetails.com/](http://www.cvedetails.com/)

#### (Quick) "Common" exploits. 

> [! WARNING ]
>  Pre-compiled binaries files. Use at your own risk

[http://web.archive.org/web/20111118031158/http://tarantula.by.ru/localroot/](http://web.archive.org/web/20111118031158/http://tarantula.by.ru/localroot/)
[http://www.kecepatan.66ghz.com/file/local-root-exploit-priv9/](http://www.kecepatan.66ghz.com/file/local-root-exploit-priv9/)

- - -

