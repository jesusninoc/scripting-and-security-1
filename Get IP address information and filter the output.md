# Get IP address information and filter the output
## Network, PowerShell 
### URL: https://www.jesusninoc.com/2014/02/07/get-ip-address-information-filter-output/
```PowerShell
Get-NetIPAddress | Where-Object -FilterScript { $_.IPAddress -match '10.0.0.69' }

```
