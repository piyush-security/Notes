- - -
## Theory : 

Services are simply programs that run in the background, accepting input or performing regular tasks. If vulnerable services are running as root, exploiting them can lead to command execution as root. 

Service exploits can be found using Searchsploit, Google, and GitHub, just like with Kernel exploits. If you want to do automatically there ame many tools which can do this.

But Here How we do it manualy!!!

- - -

## **Enumerating services** :

Show all processes that are **running as root**.

```sh
ps aux | grep "^root" --color=auto
```

## Enumerating Service Versions : 
If you found any results from the **above command**, try to identify the version number of the program being executed.

**Normally try** : 

```sh
<program-name> --version
<program-name> -v
```

**On Debian-like distributions ;**

```sh
dpkg -l | grep <program-name>
```

**On systems that use 'RPM' ;**

```sh
rpm –qa | grep <program>
```

Now Go and Find exploits On [www.Google.com](http://www.Google.com), [https://www.exploit-db.com/](https://www.exploit-db.com/), [https://github.com/](https://github.com/), use **searchsploit**.

- - -

