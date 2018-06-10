# ¿Cuál es mi IP pública?
## Network, PowerShell 
### URL: https://www.jesusninoc.com/2015/02/28/cual-es-mi-ip-publica/
```PowerShell
$resultado=Invoke-WebRequest "https://www.grc.com/x/ne.dll?bh0bkyd2"
Write-Host ($resultado.AllElements | where tagName -eq B)[12].outerText,"------------",($resultado.AllElements | where tagName -eq B)[11].outerText

```
