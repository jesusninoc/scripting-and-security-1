# Activar una aplicación que se está ejecutando
## PowerShell 
### URL: https://www.jesusninoc.com/2017/03/17/activar-una-aplicacion-que-se-esta-ejecutando-2/
```PowerShell
$WScript=New-Object -ComObject WScript.Shell
$Proceso=(Get-Process notepad).MainWindowTitle
$WScript.AppActivate($Proceso)

```
# Activar una aplicación que se está ejecutando
## PowerShell, Visual Basic 
### URL: https://www.jesusninoc.com/2016/02/16/activar-una-aplicacion-que-se-esta-ejecutando/
```PowerShell
#https://msdn.microsoft.com/en-us/library/dyz95fhy(v=vs.90).aspx

Add-Type -AssemblyName Microsoft.VisualBasic

[Microsoft.VisualBasic.Interaction]::Shell("C:\Windows\system32\notepad.exe")
[Microsoft.VisualBasic.Interaction]::AppActivate("Sin título: Bloc de notas")

```
