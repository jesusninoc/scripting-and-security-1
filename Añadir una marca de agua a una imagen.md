# Añadir una marca de agua a una imagen
## Graphics, PowerShell 
### URL: https://www.jesusninoc.com/2016/05/23/anadir-una-marca-de-agua-a-una-imagen/
```PowerShell
#Cargar imagen
$imagen = [System.Drawing.Image]::FromFile("D:\power\foto5.bmp")
#Crear Bitmap
$bmp = New-Object System.Drawing.Bitmap([int]($imagen.width)),([int]($imagen.height))
#Cargar Graphic
$dibujo = [System.Drawing.Graphics]::FromImage($bmp)
#Dibujar la marca de agua utilizando una figura de tipo rectángulo y un texto con una fuente
$dibujo.DrawImage($imagen,(New-Object Drawing.Rectangle 0,0,$imagen.Width,$imagen.Height),0,0,$imagen.Width,$imagen.Height,([Drawing.GraphicsUnit]::Pixel))
$dibujo.DrawString('Marca de agua',(New-Object System.Drawing.Font("Arial",29,[Drawing.FontStyle]'Bold' )),(New-Object Drawing.SolidBrush ([System.Drawing.Color]::Red)),0,10)
#Guardar el Bitmap
$bmp.Save('D:\power\foto5marcagua.bmp',[System.Drawing.Imaging.ImageFormat]::Bmp)
$bmp.Dispose()
$imagen.Dispose()

```
