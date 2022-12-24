- - -
## Overwriting The EIP : 

• Now we are going to overwrite the EIP. 
• In last we found the offset which is EIP's Border. 
• And The EIP is itself 4 bytes long. So..

☐ Update your exploit.py script and set the `<offset>`  variable to this value. 
☐ Set the payload variable to an empty string again.
☐ Set the retn variable to "BBBB".

☐ Save and Run the exploit.py, make sure the vulnserver is is attached and running. 
☐ Move to Debbugger and you will notice that : 
         ☐ EAX is Overwritten with bunch of “A”s. 
         ☐ EBP is 41414141. 
         ☐ But The EIP is 42424242. 
         ☐ If yes, this means we have full control over EIP now. 

☐ Now its time to set our path for ShellCode. 
















.