# Conocer el estado del ratón
## Hardware, PowerShell 
### URL: https://www.jesusninoc.com/2016/10/05/conocer-el-estado-del-raton/
```PowerShell
Get-PnpDevice | Select-Object Status,Class | Select-String "mouse"

```
