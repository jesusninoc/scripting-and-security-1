# Save screen position
## PowerShell 
### URL: https://www.jesusninoc.com/2015/01/26/save-screen-position/
```PowerShell
for (1)
{
Start-Sleep -s 10
$dY = ([System.Windows.Forms.Cursor]::Position.Y)
$dX = ([System.Windows.Forms.Cursor]::Position.X)
Write-Host $dX,$dY
$dX.ToString()+','+$dY.ToString() | Out-File F:\power\posicion.txt -Append
}

```
