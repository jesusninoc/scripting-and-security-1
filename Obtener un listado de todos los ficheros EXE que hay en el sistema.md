# Obtener un listado de todos los ficheros EXE que hay en el sistema
## PowerShell 
### URL: https://www.jesusninoc.com/2016/09/02/obtener-un-listado-de-todos-los-ficheros-exe-que-hay-en-el-sistema/
```PowerShell
Get-ChildItem c:\ "*.exe" -recurse | Select-Object FullName,Name | Out-File D:\exes.txt -Append

```
