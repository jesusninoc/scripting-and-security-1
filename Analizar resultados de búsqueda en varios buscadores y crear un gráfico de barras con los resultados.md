# Analizar resultados de búsqueda en varios buscadores y crear un gráfico de barras con los resultados
## Graphics, PowerShell 
### URL: https://www.jesusninoc.com/2015/03/03/analizar-resultados-de-busqueda-en-varios-buscadores-y-crear-un-grafico-de-barras-con-los-resultados/
```PowerShell
#Importante: utilizar las comillas correctamente en la función drawChart()

#Inicio del gráfico
$inicio="<html><head><script type=""text/javascript"" src=""https://www.google.com/jsapi""></script><script type=""text/javascript"">
google.load(""visualization"", ""1"", {packages:[""corechart""]});google.setOnLoadCallback(drawChart);function drawChart()
{var data = google.visualization.arrayToDataTable([['Nombre', 'Valor'],"
$inicio | Out-File F:\power\grafico.html

#Leer nombres en un fichero para buscar en Google
#Ejemplo de fichero:
#Bob Esponja
#Mickey Mouse
Get-Content F:\power\nombres.txt | %{

#La primera búsqueda se realiza con el nombre que aparece en el fichero en el buscador Google
$urls=’https://www.google.com/search?q=’+ $_
$result=Invoke-WebRequest $urls
$valor=($result.AllElements | ? {$_.id -eq "resultStats"}).innerText
$valor=$valor.replace("Aproximadamente","")
$valor=$valor.replace("resultados","")
$valor=$valor.replace(".","")
$valor=$valor.Trim()

#La segunda búsqueda se realiza con el nombre que aparece en el fichero en el buscador Bing
$urls=’https://www.bing.com/search?q=’+ $_
$result=Invoke-WebRequest $urls
$valor2=($result.AllElements | ? {$_.class -eq “sb_count”}).innerText
$valor2=$valor2.replace("resultados","")
$valor2=$valor2.replace(".","")
$valor2=$valor2.Trim()

Write-Host $_
Write-Host $valor
Write-Host $valor2

$valorg=$_+' Google'
$valorb=$_+' Bing'
"['$valorg', $valor]," | Out-File F:\power\grafico.html -Append
"['$valorb', $valor2]," | Out-File F:\power\grafico.html -Append
}

#Final del gráfico
$fin="]);var options = {title: 'Valoracion de nombres',vAxis: {title: 'Nombre', titleTextStyle:
{color: 'red'}}};var chart = new google.visualization.BarChart(document.getElementById('chart_div'));chart.draw(data, options);}
</script></head><body><div id=""chart_div"" style=""width: 900px; height: 500px;""></div></body></html>"

$fin | Out-File F:\power\grafico.html -Append

```
