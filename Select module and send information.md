# Select module and send information
## PowerShell, Processes 
### URL: https://www.jesusninoc.com/2013/01/09/select-module-and-send-information/
```PowerShell
$a=Get-Process -Module | Group-Object | Select-Object name
foreach($mem in $a){
$ap=[String]$mem.name.replace("System.Diagnostics.ProcessModule ","")
$ap=$ap.ToLower()
$ap=$ap.replace("(","")
$ap=$ap.replace(")","")
$ap=$ap.replace(".dll","")
$ap=$ap.replace(".exe","")
$urls="https://www.procexample.com"+$ap
$urls
$result=Invoke-WebRequest $urls
$en=$result.AllElements | ? {$_.tagName -eq “DIV”}
foreach($aen in $en.innerText){
$aen
}
}

```
