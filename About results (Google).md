# About results (Google)
## PowerShell 
### URL: https://www.jesusninoc.com/2014/10/06/about-results-google/
```PowerShell
$urls="https://www.google.com/search?q=powershell"
$result=Invoke-WebRequest $urls
$en=$result.AllElements | ? {$_.id -eq “resultStats”}
foreach($aen in $en.innerText){
$aen
}

```
