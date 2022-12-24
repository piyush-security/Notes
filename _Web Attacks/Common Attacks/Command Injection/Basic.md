- - -
<mark style="background: #FFB86CA6;">useful</mark> : [command-injection-payload-list](https://github.com/payloadbox/command-injection-payload-list)

## Fuzzing : 

```sh
wfuzz -c -z file,"/usr/share/payloadsallthethings/Command Injection/Intruder/command-execution-unix.txt" --sc 200 "$URL/index.php?parameter=idFUZZ"
```

