# Ver información en el Registro de Windows sobre dispositivos conectados por USB
## Hardware, PowerShell, Registry 
### URL: https://www.jesusninoc.com/2015/03/07/ver-informacion-en-el-registro-de-windows-sobre-dispositivos-conectados-por-usb/
```PowerShell
Get-ItemProperty -Path 'Registry::HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Enum\USBSTOR\*\*\' | Where-Object { $_.FriendlyName }
Get-ItemProperty -Path 'Registry::HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Enum\USB\*\*\' | Where-Object { $_.FriendlyName }
Get-ItemProperty -Path 'Registry::HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Enum\USB\*\*\' | Where-Object { $_.FriendlyName }
Get-ItemProperty -Path 'Registry::HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Enum\USBSTOR\*\*\' | Where-Object { $_.FriendlyName }

```
