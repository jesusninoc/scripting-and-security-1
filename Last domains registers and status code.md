# Last domains registers and status code
## PowerShell, Servers, Web scraping 
### URL: https://www.jesusninoc.com/2014/02/04/last-domains-registers-and-status-code/
```PowerShell
#It doesn't work
$ur='https://es.wsdata.co/2015-12-28/domains-list.html'
foreach($u in (((Invoke-WebRequest $ur).AllElements).where{$_.class -eq "responsive"}).innerHTML -split '[\r\n]' |%{if($_ -match 'href'){$_ -replace "<.*?>"}})
{
    $u
    (Invoke-WebRequest $u).StatusCode
}

```
