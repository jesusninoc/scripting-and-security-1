# Path to the executable file of the process
## PowerShell, Processes 
### URL: https://www.jesusninoc.com/2016/10/07/path-to-the-executable-file-of-the-process/
```PowerShell
Get-Process | Select-Object Name,Path
Get-WmiObject -Class win32_process | Select-Object Name,ExecutablePath

```
