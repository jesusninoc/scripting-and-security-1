# Ver la temperatura del equipo
## Hardware, PowerShell 
### URL: https://www.jesusninoc.com/2016/08/25/ver-la-temperatura-del-equipo/
```PowerShell
$Temperatura=Get-WmiObject MSAcpi_ThermalZoneTemperature -Namespace "root/wmi"
$Kelvin = $Temperatura.CurrentTemperature / 10
$Celsius = $Kelvin - 273.15
$Celsius.ToString() + " C "

```
