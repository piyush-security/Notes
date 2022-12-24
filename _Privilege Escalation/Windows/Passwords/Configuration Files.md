- - -
Some Administrators leave **Configuration** **Files** on the system with **passwords** in them.

The **Unattended.xml** is the **example** of this.

It allows for the largely automated setup of Windows systems.

> [! Note ] 
> Running these command in the ‘ C:\ ’ will not be recoomeded.

Recursively search for files in the current directory with “**pass**” in the name, or ending in “**.config**” :

```cmd
dir /s *pass* == *.config
```

Recursively search for files in the current directory that contains word “password” and also end in either .xml, .ini, .txt :

```cmd
findstr /si password *.xml *.ini *.txt
```

If the Files Found Copy those files to kali then analysing it will be better.

- - -

