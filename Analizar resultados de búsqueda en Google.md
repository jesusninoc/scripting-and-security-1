# Analizar resultados de búsqueda en Google
## PowerShell 
### URL: https://www.jesusninoc.com/2015/01/24/analizar-resultados-de-busquedas-en-google/
```PowerShell
#Leer nombres en un fichero para realizar la búsqueda en Google
Get-Content F:\power\nombres.txt | %{

#La primera búsqueda se realiza con el nombre que aparece en el fichero
$urls='https://www.google.com/search?q='+ $_ +''
$result=Invoke-WebRequest $urls
$valor=($result.AllElements | ? {$_.id -eq “resultStats”}).innerText
$valor=$valor.replace("Aproximadamente","")
$valor=$valor.replace("resultados","")
$valor=$valor.Trim()
Write-Host $_
Write-Host $valor

#La segunda búsqueda se realiza con el nombre que aparece en el fichero convertido a minúsculas
$lower=$_.tolower()
$urls='https://www.google.com/search?q='+ $lower +''
$result=Invoke-WebRequest $urls
$valor=($result.AllElements | ? {$_.id -eq “resultStats”}).innerText
$valor=$valor.replace("Aproximadamente","")
$valor=$valor.replace("resultados","")
$valor=$valor.Trim()
Write-Host $lower
Write-Host $valor

#La tercera búsqueda se realiza con el nombre que aparece en el fichero convertido a mayúsculas
$upper=$_.ToUpper()
$urls='https://www.google.com/search?q='+ $upper +''
$result=Invoke-WebRequest $urls
$valor=($result.AllElements | ? {$_.id -eq “resultStats”}).innerText
$valor=$valor.replace("Aproximadamente","")
$valor=$valor.replace("resultados","")
$valor=$valor.Trim()
Write-Host $upper
Write-Host $valor
}

```
