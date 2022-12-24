- - -
## Finding The write module :

• Go to [https://github.com/corelan/mona](https://github.com/corelan/mona) .
• Download the mona.py script and drop mona.py into the 'PyCommands' folder (inside the Immunity Debugger application folder).

• Rerun the Immunity-debbugger....

Go to Debbugger and type on the bottom bar : 

```
!mona modules
```

![Imgur](https://i.imgur.com/LKcfYUg.png)

Notice the Protection setting, Everything set to Flase . 
- Select something attached to vulnserver itself and set all protections top Flase. 
- Note the name of your selected module. 

Go to kali's terminal.  And Run : 

```ruby
/usr/share/metaspoloit-framework/tools/exploit/nasm_shell.rb
nasm> JMP ESP 
```

![Imgur](https://i.imgur.com/GcRw7KM.png)

Move back to Debbugger and type :

```
!mona find -s “\xff\xe4” -m <module_name>
```

![500](https://i.imgur.com/nYGogRr.png)

Now look for the retun address. Start from the top one. Copy the return address. 
![Imgur](https://i.imgur.com/6sl04BB.png)

Go back to kali. 
☐ Open Your exploit.py Script. 
      ☐	remove the whole badchars from payload variable. 
      ☐ replace the 4 “B”s  from the retn variable with <return_address> But : 
               ☐  For example your selected return address is 625011af.
               ☐ So, we will write this as “\xaf\x11\x50\x62”  
      ☐ Save the exploit.py. 
☐ Move back to Immunity. 
☐ And click on the little blue arrow. 
![Imgur](https://i.imgur.com/0JlOroi.png)


☐ And paste your retun Address. ( like this : 625011af )  ,  Then hit OK.
☐ Click F2 on your keyboard.  ( And we have set our break-point ). 

☐ move back to kali. 
☐ rerun the exploit.py. 
☐ Move back to Immunity. And you will Notice : 
 			☐ In the bottom, “Breakpoint at <module_name>.<retun_address>  ”
 			☐ The program is paused. 
 			☐ And the EIP is Overwritten with our selected return address. 

☐  Now Give this whole process a cute finishing touch. 

- - -



