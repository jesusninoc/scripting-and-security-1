# Read cursor position
## Graphics, PowerShell 
### URL: https://www.jesusninoc.com/2014/12/28/read-cursor-position/
```PowerShell
for ()
{
$dX = ([System.Windows.Forms.Cursor]::Position.X ) #X coordinates
$dY = ([System.Windows.Forms.Cursor]::Position.Y ) #Y coordinates
Write-Host $dX,$dY #print X and Y
}

```
