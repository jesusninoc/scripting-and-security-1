# Ejecutar un script de JavaScript en Internet Explorer mediante PowerShell
## JavaScript, PowerShell 
### URL: https://www.jesusninoc.com/2016/03/26/ejecutar-un-script-de-javascript-en-internet-explorer-mediante-powershell/
```PowerShell
$ie = New-Object -com "InternetExplorer.Application"
$ie.Navigate("about:blank")
$ie.visible = $true

$ie.document.write("<script>alert(""hola"") </script>")

```
