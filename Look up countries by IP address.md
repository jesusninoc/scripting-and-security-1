# Look up countries by IP address
## Network, PowerShell, Web Service 
### URL: https://www.jesusninoc.com/2016/02/01/look-up-countries-by-ip-address/
```PowerShell
$ip=New-WebServiceProxy -uri "https://www.webservicex.net/geoipservice.asmx?WSDL"
$ip.GetGeoIP('8.8.8.8') | Select-Object CountryName

```
