- - -
## Spiking : 

> [! Note ]
> Turn Off the windows Defender, Anti-viruses, firewall.
> Run Vulnserver. ( As admin )
> Run Immunity Debbuger ( As admin )
> Attach the vulnserver to immunity-debbugger and run it.

• Identifing the vulnerable thing/option/stuff in the program. 
• To do this we will perform spiking. 

![Imgur](https://i.imgur.com/YyFClyH.png)

To use this tools we have to write a basic **.spk** script.

```spk
s_readline();  
s_string("TRUN ");  
s_string_variable("0");
```

Save this script as **something.spk**. 
**Change** the “**TRUN**” Options with the option you want to test.
Now Run it. 

![Imgur](https://i.imgur.com/Uipvf9s.png)

Note this will send lots of requests. 
If the Options is vulnerable, then the program will crash/pause at immunity-debbugger. 
If not, Stop the script and move-on to next option. 

- - -





