# ¿El procesador es Intel?
## Hardware, PowerShell 
### URL: https://www.jesusninoc.com/2016/06/14/el-procesador-es-intel/
```PowerShell
if((Get-WmiObject Win32_Processor).Caption -match "Intel"){"Intel"}else{"No es Intel"}
```
