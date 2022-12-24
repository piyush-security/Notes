- - -
## Finding Bad Chars :

• Now before generating ShellCode, we need to know what characters are good for the shellcode and what are not.
• Now go to https://github.com/cytopia/badchars .
☐ copy the python's badchars bunch.
☐ Set the payload variable to the string of bad-chars and save it.

• Now follow the following steps.
☐ Run the exploit.py
☐ Moving on Debbugger windows. Everything looks same as last time( EIP Overwrite ).

☐ Select the ESP Value >>> right click >>> Follow in Dump.
☐ Now move on to 3rd Column of Debbuger. >>> right click >>> Apperiance >>> font >>> OEM....
☐ Now Look at the Dumped-Chars carefully.
☐ read the whole chars from “ 01 - ff ” and from the starting find the first badchar.
☐ Note that BadChar in your notes. Open exploit.py and remove the `<badchar>` we found.
☐ save the exploit.py.
☐ rerun the Immunity and then exploi.py.
☐ Follow these ( ☐ ) steps until you get every bad-char removed.
- - -




















.
