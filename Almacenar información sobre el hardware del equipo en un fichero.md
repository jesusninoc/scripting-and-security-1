# Almacenar información sobre el hardware del equipo en un fichero
## Hardware, PowerShell 
### URL: https://www.jesusninoc.com/2016/06/19/almacenar-informacion-sobre-el-hardware-del-equipo-en-un-fichero/
```PowerShell
(Get-WmiObject Win32_AutochkSetting).SettingID | Out-File inf.txt -Append
(Get-WmiObject Win32_BaseBoard).Manufacturer | Out-File inf.txt -Append
(Get-WmiObject Win32_BIOS).Version | Out-File inf.txt -Append
(Get-WmiObject Win32_Bus).DeviceID | Out-File inf.txt -Append
Get-WmiObject Win32_Processor | Out-File inf.txt -Append
Get-WmiObject Win32_SystemEnclosure | Out-File inf.txt -Append
Get-WmiObject Win32_Battery | Out-File inf.txt -Append
Get-WmiObject Win32_Printer | Out-File inf.txt -Append

```
