# View any connected USB device on your system
## Hardware, PowerShell 
### URL: https://www.jesusninoc.com/2015/03/06/view-any-connected-usb-device-on-your-system/
```PowerShell
Get-WmiObject Win32_USBControllerDevice |%{[wmi]($_.Dependent)} | Sort-Object Manufacturer,Description,DeviceID | ft -GroupBy Manufacturer Description,Service,DeviceID

```
