# Search in the Public MA-L Listing (for example MAC)
## Database, Network, PowerShell, Security 
### URL: https://www.jesusninoc.com/2014/05/16/search-the-public-ma-l-listing-example-mac/
```PowerShell
#Searching the list will allow you to determine whether your company or any parent/subsidiary companies already own an assignment. When searching the public listing, addresses should be entered as XX-XX-XX.

#Group by MAC in ARP
#https://www.jesusninoc.com/powershell/2014/05/12/group-by-mac-in-arp/
$all=””
$arps=arp -a
foreach($line in $arps)
{
if($line -match “mico”)
{
$a=$line.Replace(” “,” “)
$a=$a.Split(” “)
$all=$all+”*”+$a[9]
}
}

#Search MAC in https://standards.ieee.org/
foreach($mac in ($all.Split(“*”) | Group-Object).name)
{
$mac.Substring(0,8)
$url="https://standards.ieee.org/cgi-bin/ouisearch?"+$mac.Substring(0,8)
$result=Invoke-WebRequest $url
#Here are the results of your search through the public section of the IEEE Standards MA-L database report for MAC
$result.AllElements | Where tagName -eq “PRE”
}

```
