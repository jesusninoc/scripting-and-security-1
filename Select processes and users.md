# Select processes and users
## PowerShell, Processes 
### URL: https://www.jesusninoc.com/2013/02/02/select-process-and-user/
```PowerShell
Get-WmiObject win32_process |% {Write-Host $_.processname $_.getowner().user}

```
