# Save information about MAC (search the Public MA-L Listing)
## Database, Network, PowerShell 
### URL: https://www.jesusninoc.com/2014/12/01/save-information-mac-search-public-ma-l-listing/
```PowerShell
#Search MAC in https://standards.ieee.org/
#Group by MAC
$macs=gc .\mac.txt | Group-Object
#List MAC
foreach($mac in $macs.Name)
{
$mac.Substring(0,8)
$url=”https://standards.ieee.org/cgi-bin/ouisearch?”+$mac.Substring(0,8)
$result=Invoke-WebRequest $url
#Here are the results of your search through the public section of the IEEE Standards MA-L database report for MAC
$res=$result.AllElements | Where tagName -eq “PRE”
#Save MAC, IP, and information about MAC
$ip = arp -a | select-string "$mac" |% { $_.ToString().Trim().Split(" ")[0] }
$mac,$ip, $res.innerText | Out-File list.txt -Append
}

```
