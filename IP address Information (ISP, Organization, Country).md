# IP address Information (ISP, Organization, Country)
## Network, PowerShell 
### URL: https://www.jesusninoc.com/2014/10/12/ip-address-information-isp-organization-country/
```PowerShell
Get-Content 'C:\ips.txt' | Sort-Object | Group-Object | % {
$ip=$_.name
$url='https://www.speedguide.net/ip/'+$ip
$url
$result = Invoke-WebRequest $url
$result.AllElements | Where Class -eq “t1 ip-info” | %{$_.innerText}
sleep -Seconds 5
}

```
