# Buscar un nombre dentro de la lista de deudores publicada por la Agencia Tributaria (nueva versión)
## PowerShell 
### URL: https://www.jesusninoc.com/2016/06/30/buscar-un-nombre-dentro-de-la-lista-de-deudores-publicada-por-la-agencia-tributaria-nueva-version/
```PowerShell
#Pasos para poder buscar un nombre dentro de la lista de deudores publicada por la Agencia Tributaria:
#1. Descargar el PDF: https://www.agenciatributaria.gob.es/static_files/AEAT_Sede/NoIx/Listado_deudores_Art95bisLGT.pdf
#2. Dividir el fichero PDF en páginas: https://www.splitpdf.com/es
#3. Convertir cada página del PDF en PNG: https://www.jesusninoc.com/2015/12/27/convert-pdf-to-png/
#4. Convertir cada PNG en TXT: https://www.jesusninoc.com/2015/12/27/convert-png-to-text/
#5. Buscar una palabra dentro del TXT: Select-String

ls 'D:\power\pdf\pdf\convertir\deudores' *.png | %{
$ficheropng=$_.FullName
$ficherosin=$_.FullName.Replace('.png','')
D:\power\tesseract-ocr-3.02-win32-portable\Tesseract-OCR\tesseract.exe $ficheropng $ficherosin
gc $ficherosin'.txt' | Select-String 'moroso'
}

```
