# Determinar si un objeto es igual a otro
## PowerShell, Visual Basic 
### URL: https://www.jesusninoc.com/2016/02/16/determinar-si-un-objeto-es-igual-a-otro/
```PowerShell
#https://msdn.microsoft.com/es-es/library/bsc2ak47(v=vs.110).aspx

Add-Type -AssemblyName Microsoft.VisualBasic

$i=10
$diez="10"
[Microsoft.VisualBasic.Interaction]::Equals($i,$diez)
[Microsoft.VisualBasic.Interaction]::Equals("hola","hola")
[Microsoft.VisualBasic.Interaction]::Equals("holas","hola")

```
