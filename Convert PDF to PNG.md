# Convert PDF to PNG
## PowerShell 
### URL: https://www.jesusninoc.com/2015/12/27/convert-pdf-to-png/
```PowerShell
#ImageMagick Convert Command-Line Tool
#Use the convert program to convert between image formats as well as resize an image, blur, crop, despeckle, dither, draw on, flip, join, re-sample, and much more. See Command Line Processing for advice on how to structure your convert command or see below for example usages of the command.

cd 'C:\Program Files\ImageMagick-6.9.2-Q16'
ls 'D:\power\pdf\pdf\convertir' *.pdf | %{.\convert -density 150 $_.FullName -quality 90 $_.FullName.Replace('pdf','png')}

```
