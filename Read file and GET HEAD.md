# Read file and GET HEAD
## PowerShell, Security 
### URL: https://www.jesusninoc.com/2014/02/20/read-file-and-get-head/
```PowerShell
#fic.txt: https://www.jesusninoc.com/powershell

foreach($urls in Get-Content F:\power\fic.txt)
{
$resulta=Invoke-WebRequest $urls
foreach($a in $resulta.AllElements)
{
if($a.innerHTML.Contains("HEAD"))
{
$a.innerHTML
}
}
sleep -milliseconds 100
}

```
