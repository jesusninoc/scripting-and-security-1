# Añadir una marca de agua a un vídeo MP4
## Graphics, Multimedia, PowerShell 
### URL: https://www.jesusninoc.com/2016/03/11/anadir-una-marca-de-agua-a-un-video-mp4/
```PowerShell
D:\program\ffmpeg\bin\ffmpeg.exe -i D:\power\video\thesmash.mp4 -f image2 -pix_fmt bgr8 D:\power\video\capturas2\%01d.bmp

```
```PowerShell
#Cargar System.Drawing
[Reflection.Assembly]::LoadWithPartialName("System.Drawing")
#Listar imágenes 
Get-ChildItem D:\power\video\capturas2 | %{
#Listar cada imagen
$_
#Cargar imagen
$imagen = [System.Drawing.Image]::FromFile($_.FullName)
#Crear Bitmap
$bmp = New-Object System.Drawing.Bitmap([int]($imagen.width)),([int]($imagen.height))
#Cargar Graphic
$dibujo = [System.Drawing.Graphics]::FromImage($bmp)
#Dibujar la marca de agua utilizando una figura de tipo rectángulo y un texto con una fuente
$dibujo.DrawImage($imagen,(New-Object Drawing.Rectangle 0,0,$imagen.Width,$imagen.Height),0,0,$imagen.Width,$imagen.Height,([Drawing.GraphicsUnit]::Pixel))
$dibujo.DrawString('Marca de agua',(New-Object System.Drawing.Font("Arial",29,[Drawing.FontStyle]'Bold' )),(New-Object Drawing.SolidBrush ([System.Drawing.Color]::Red)),0,10)
#Guardar el Bitmap
$bmp.Save('D:\power\video\capturas3\'+$_.Name,[System.Drawing.Imaging.ImageFormat]::Bmp)
$bmp.Dispose()
$imagen.Dispose()
}

```
```PowerShell
D:\program\ffmpeg\bin\ffmpeg.exe -i D:\power\video\capturas3\%01d.bmp -r 10 D:\power\video\thesmash23.mp4

```
