# How to identify different versions of Windows
## PowerShell 
### URL: https://www.jesusninoc.com/2014/05/01/identify-different-versions-windows/
```PowerShell
(Get-WmiObject -ComputerName . Win32_OperatingSystem -ea stop).Version

```
