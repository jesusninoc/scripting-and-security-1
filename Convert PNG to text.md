# Convert PNG to text
## PowerShell 
### URL: https://www.jesusninoc.com/2015/12/27/convert-png-to-text/
```PowerShell
#Tesseract OCR
#Tesseract is probably the most accurate open source OCR engine available. Combined with the Leptonica Image Processing Library it can read a wide variety of image formats and convert them to text in over 60 languages. It was one of the top 3 engines in the 1995 UNLV Accuracy test. Between 1995 and 2006 it had little work done on it, but since then it has been improved extensively by Google. It is released under the Apache License 2.0.

ls 'D:\power\pdf\pdf\convertir\deudores' *.png | %{
D:\power\tesseract-ocr-3.02-win32-portable\Tesseract-OCR\tesseract.exe $_.FullName $_.FullName.Replace('png','')
}

```
