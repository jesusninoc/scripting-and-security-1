# Number of cores
## Hardware, PowerShell 
### URL: https://www.jesusninoc.com/2015/11/20/number-of-cores/
```PowerShell
Get-WmiObject -Class Win32_Processor | Select-Object NumberOfCores

```
