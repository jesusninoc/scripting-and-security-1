# Drive size
## PowerShell 
### URL: https://www.jesusninoc.com/2014/03/25/drive-size/
```PowerShell
Get-WmiObject -Class Win32_LogicalDisk | Select-Object deviceid, size

```
