# Obtener enlaces de Youtube (recorriendo las páginas de resultados)
## Automation, PowerShell, Web scraping 
### URL: https://www.jesusninoc.com/2016/08/06/obtener-enlaces-de-youtube-recorriendo-las-paginas-de-resultados/
```PowerShell
#Paso 1: Obtener enlaces de resultados
$url="https://www.youtube.com/results?search_query=no+dolls"
$result = Invoke-WebRequest $url
$pageresults=$result.Links.href | Select-String "\?sp=S"
foreach($page in $pageresults)
{
    #Paso 2: Obtener enlaces de Youtube para cada página de resultados
    Start-Sleep -Seconds 5
    $urlpage="https://www.youtube.com/"+$page
    $resultpage = Invoke-WebRequest $urlpage
    ($resultpage.Links.href | Select-String "watch" | Group-Object).Name | %{"https://www.youtube.com"+$_}
}

```
