# Averiguar si una dirección IP es estática
## Network, PowerShell 
### URL: https://www.jesusninoc.com/2016/09/13/averiguar-si-una-direccion-ip-es-estatica/
```PowerShell
$ip='90.0.0.0'
$result=(Resolve-DnsName $ip).NameHost
if($result -match 'static'){$ip + ' static'}
else{$result + ' no static'}

```
