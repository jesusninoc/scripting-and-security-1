# Eliminar archivos modificados en el último día
## Filesystem, PowerShell 
### URL: https://www.jesusninoc.com/2016/02/15/eliminar-archivos-modificados-en-el-ultimo-dia/
```PowerShell
Get-ChildItem | Where-Object {$_.LastWriteTime -ge (Get-Date).AddDays(-1)} | Remove-Item

```
