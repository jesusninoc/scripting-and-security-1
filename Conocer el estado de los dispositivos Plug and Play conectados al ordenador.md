# Conocer el estado de los dispositivos Plug and Play conectados al ordenador
## Hardware, PowerShell 
### URL: https://www.jesusninoc.com/2015/05/25/conocer-el-estado-de-los-dispositivos-plug-and-play-conectados-al-ordenador/
```PowerShell
(Get-CimInstance Win32_PnPEntity) | Select-Object Name, Status

```
