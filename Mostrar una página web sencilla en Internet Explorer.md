# Mostrar una página web sencilla en Internet Explorer
## PowerShell, Web 
### URL: https://www.jesusninoc.com/2016/03/21/mostrar-una-pagina-web-sencilla-en-internet-explorer/
```PowerShell
$oIE=new-object -com internetexplorer.application
$oIE.navigate2("About:blank")
while ($oIE.busy) {
    sleep -milliseconds 50
}
$oIE.visible=$true

$params=[String]"<html><body>Hola</body></html>"

$oIE.document.write($params)

```
