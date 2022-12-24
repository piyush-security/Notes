- - -
Official Docs : https://bloodhound.readthedocs.io/en/latest/index.html
- - -
### Installation :  

```sh
sudo apt install bloodhound -y 
```

- - -
## Usage :  

```sh
neo4j console 
```

Visit to the http://localhost:7687 . use neo4j:neo4j 
close your browser 

```sh
bloodhound 
```

Now, Download [this]([this](https://github.com/BloodHoundAD/BloodHound/blob/master/Collectors/SharpHound.ps1)) and transfer it to windows. 

```powershell
PS> powershell -ep bypass 
PS> . .\SharpHound.ps1 
PS> Invoke-BloodHound -CollectionMethod All -Domain Marvel.local -ZipFileName myfile.zip 
```

Now,  Transfer this “**myfile.zip**” to kali

Then Move to Bloodhound : 

Inside Bloodhound.

```r
☐ Click on “Upload Data” button, 4th option right-side. 
☐ select your “myfile.zip” 
☐ Click on queries 
☐ Now Enumerate!!! 
☐ Target Bigger accounts Like : Domain admin, DC. 
```

- - -