# Analizar información obtenida sobre las actualizaciones (Get-HotFix)
## PowerShell, Updates 
### URL: https://www.jesusninoc.com/2015/01/25/analizar-informacion-obtenida-sobre-las-actualizaciones-get-hotfix/
```PowerShell
Get-HotFix | Group-Object Description

```
```PowerShell
Get-HotFix | Sort-Object InstalledOn

```
```PowerShell
$kb=Read-Host 'NúmeroActualización'
((Get-HotFix).hotfixid | Select-String $kb)

```
