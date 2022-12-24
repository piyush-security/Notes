- - -
### Installation : 

```sh
sudo apt-get install powershell -y
```

Start up a PowerShell session : 

```sh
pwsh
```

Clone the Invoke-Obfuscation GitHub repository that contains the Invoke-Obfuscation PowerShell scripts.

```powershell
git clone https://github.com/danielbohannon/Invoke-Obfuscation.git
```

- - -
Launch the `Invoke-Obfuscation` script. 
This is used to encode **powershell** code/scripts.

```powershell
cd ./Invoke-Obfuscation/
Import-Module ./Invoke-Obfuscation.psd1
cd ..
Invoke-Obfuscation
```

You can also use i=otherr method provided by this tool. 
```powershell
Invoke-Obfuscation> SET SCRIPTPATH /PATH/TO/YOUR/SHELL.PS1
Invoke-Obfuscation> ENCODING
Invoke-Obfuscation> 5 
 < Copy the result and use it >
```

- - -



