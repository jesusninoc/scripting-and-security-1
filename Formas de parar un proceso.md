# Formas de parar un proceso
## PowerShell, Processes 
### URL: https://www.jesusninoc.com/2015/01/20/formas-de-parar-un-proceso/
```PowerShell
Get-Process -Name notepad | Stop-Process

```
```PowerShell
Get-WmiObject -Class Win32_Process -Filter “name=’notepad.exe'” | Invoke-WmiMethod -Name Terminate

```
```PowerShell
Get-Process -Name notepad | ForEach-Object -Process {$_.Kill()}

```
