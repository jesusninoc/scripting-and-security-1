# Aclarar una imagen utilizando ImageMagick y convertir a texto con Tesseract
## Automation, Graphics, PowerShell, Security 
### URL: https://www.jesusninoc.com/2015/02/09/aclarar-una-imagen-utilizando-imagemagick-y-convertir-a-texto-con-tesseract/
```PowerShell
ls F:\power\SampleImages\ | %{
#Proceso para aclarar la imagen
#Carpeta de ImageMagick
cd ‘C:\Program Files\ImageMagick-6.9.0-Q16’
$_.Name
$fichero=$_.FullName
#Nombre del nuevo fichero con los cambios que se aplicaran
$ficheronuevo='F:\power\SampleImagesConvert\'+'N-'+$_.Name
#Cambios en: Brillo, contraste, Auto Gamma y Filtro (por defecto 4)
.\convert.exe $fichero -resize 360x100 -quality 95 -brightness-contrast 45 -auto-gamma -median 4 $ficheronuevo
#Proceso para convertir la imagen en texto
cd ‘C:\Program Files (x86)\Tesseract-OCR’
.\tesseract.exe $ficheronuevo $ficheronuevo.Replace('jpg','txt') -l spa
}

```
