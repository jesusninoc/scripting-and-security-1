# Cambiar el User-Agent
## Network, PowerShell 
### URL: https://www.jesusninoc.com/2015/07/09/cambiar-el-user-agent/
```PowerShell
$useragent='Mozilla/5.0 (Windows NT; Windows NT 6.2; es-ES) WindowsPowerShell/5.0'
$url='www.jesusninoc.com'
Invoke-WebRequest -Uri $url -UserAgent $useragent

```
