# Search in Google
## PowerShell 
### URL: https://www.jesusninoc.com/2012/04/23/search-in-google/
```PowerShell
$IE= new-object -com InternetExplorer.Application
$IE.navigate2("https://www.google.es/search?q=powershell")

while ($IE.busy) {
sleep -milliseconds 100
}

$IE.visible=$true
$IE.Document.getElementById(“lst-ib”).value=”Scripting and security”
$IE.Document.getElementById("_fZl").click()

```
