# Version of Windows in which the process is running
## PowerShell, Processes 
### URL: https://www.jesusninoc.com/2016/11/16/version-of-windows-in-which-the-process-is-running/
```PowerShell
Get-WmiObject -Class win32_process | Select-Object WindowsVersion

```
