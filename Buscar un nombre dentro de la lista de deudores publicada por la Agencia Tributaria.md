# Buscar un nombre dentro de la lista de deudores publicada por la Agencia Tributaria
## PowerShell 
### URL: https://www.jesusninoc.com/2015/12/28/buscar-un-nombre-dentro-de-la-lista-de-deudores-publicada-por-la-agencia-tributaria/
```PowerShell
#Pasos para poder buscar un nombre dentro de la lista de deudores publicada por la Agencia Tributaria:
#1. Descargar el PDF: https://www.agenciatributaria.es/AEAT.internet/Inicio/_componentes_/_Le_interesa_conocer/Publicacion_del_listado_de_deudores_a_la_Hacienda_Publica__art__95_bis_LGT_.shtml
#2. Dividir el fichero PDF en páginas: https://www.splitpdf.com/es
#3. Convertir cada página del PDF en PNG: https://www.jesusninoc.com/2015/12/27/convert-pdf-to-png/
#4. Convertir cada PNG en TXT: https://www.jesusninoc.com/2015/12/27/convert-png-to-text/
#5. Buscar una palabra dentro del TXT: Select-String

ls 'D:\power\pdf\pdf\convertir\deudores' *.png | %{
$ficheropng=$_.FullName
$ficherosin=$_.FullName.Replace('.png','')
D:\power\tesseract-ocr-3.02-win32-portable\Tesseract-OCR\tesseract.exe $ficheropng $ficherosin
gc $ficherosin'.txt' | Select-String 'empresa'
}

```
