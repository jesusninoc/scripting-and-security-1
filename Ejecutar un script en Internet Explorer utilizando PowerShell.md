# Ejecutar un script en Internet Explorer utilizando PowerShell
## JavaScript, PowerShell, Web 
### URL: https://www.jesusninoc.com/2016/03/22/ejecutar-un-script-en-internet-explorer-utilizando-powershell/
```PowerShell
$oIE=new-object -com internetexplorer.application
$oIE.navigate2("About:blank")
while ($oIE.busy) {
    sleep -milliseconds 50
}
$oIE.visible=$true

$params=[String]'
<html>
<head>
<script>
function funcion(){document.getElementById("cambiar").innerHTML = "Cambiar texto";}
</script>
</head>
<body>
<h1>Web cambiar texto</h1>
<p id="cambiar">Texto sin cambiar</p>
</body>
</html>'

$oIE.document.write($params)
Start-Sleep -Seconds 10
$oIE.document.write("<script>funcion()</script>")

```
