# Resolves a host name or IP address to an IPHostEntry instance
## Network, PowerShell, Servers 
### URL: https://www.jesusninoc.com/2015/02/28/resolves-host-name-ip-address-iphostentry-instance/
```PowerShell
$IPAddress='8.8.8.8'
[Net.DNS]::GetHostEntry($IPAddress)

```
