# Convertir imagen a texto
## Automation, PowerShell, Security 
### URL: https://www.jesusninoc.com/2015/12/20/convertir-imagen-a-texto/
```PowerShell
ls 'D:\power\images\' *.png | %{D:\power\tesseract-ocr-3.02-win32-portable\Tesseract-OCR\tesseract.exe $_.FullName $_.FullName.Replace('png','txt')}

```
