# Realizar una captura de pantalla y dividir en partes la captura
## Graphics, PowerShell 
### URL: https://www.jesusninoc.com/2015/02/02/realizar-captura-de-pantalla-y-dividir-en-partes-la-captura/
```PowerShell
#Abrir por ejemplo google.es y realizar una búsqueda

[Reflection.Assembly]::LoadWithPartialName("System.Drawing")
function screenshot([Drawing.Rectangle]$bounds, $path)
{
$bmp = New-Object Drawing.Bitmap $bounds.width, $bounds.height
$graphics = [Drawing.Graphics]::FromImage($bmp)
$graphics.CopyFromScreen($bounds.Location, [Drawing.Point]::Empty, $bounds.size)
$bmp.Save($path)
$graphics.Dispose()
$bmp.Dispose()
}

for($i=220; $i -ne 720; $i+=100)
{
$i
$bounds = [Drawing.Rectangle]::FromLTRB(120, $i, 680, $i+100)
$fichero='F:\power\captura'+$i+'.png'
#Realizar captura
screenshot $bounds $fichero
}

```
