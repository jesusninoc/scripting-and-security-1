# Cambiar la página de inicio en Internet Explorer desde el Registro de Windows
## PowerShell 
### URL: https://www.jesusninoc.com/2016/06/04/cambiar-la-pagina-de-inicio-en-internet-explorer-desde-el-registro-de-windows/
```PowerShell
$RegKey =’HKCU:\Software\Microsoft\Internet Explorer\Main\’
Set-ItemProperty -Path $RegKey -Name ‘Start Page’ -Value ‘https://www.jesusninoc.com/’

```
