# Descargar enlaces de Youtube (recorriendo las páginas de resultados)
## Automation, PowerShell, Web scraping 
### URL: https://www.jesusninoc.com/2016/08/10/descargar-enlaces-de-youtube-recorriendo-las-paginas-de-resultados/
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
    ($resultpage.Links.href | Select-String "watch" | Group-Object).Name | %{
        #Paso 3: Descargar cada enlace de Yotube con youtube-dl (descargar youtube-dl en https://rg3.github.io/youtube-dl/download.html)
        $urldownload="https://www.youtube.com"+$_
        Start-Sleep -Seconds 5
        Set-Location D:\
        D:\youtube-dl.exe $urldownload
        }
}

```
