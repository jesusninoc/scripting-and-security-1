# Herramienta para parar procesos
## PowerShell, Processes 
### URL: https://www.jesusninoc.com/2015/11/21/herramienta-para-parar-procesos/
```PowerShell
Get-Process | Out-GridView -PassThru | Stop-Process

```
