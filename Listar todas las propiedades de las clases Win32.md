# Listar todas las propiedades de las clases Win32
## PowerShell 
### URL: https://www.jesusninoc.com/2016/01/22/listar-todas-las-propiedades-de-las-clases-win32/
```PowerShell
(Get-WmiObject -List).name | Select-String Win32 | %{
$_
pause
Get-WmiObject -Class $_
pause
}

```
