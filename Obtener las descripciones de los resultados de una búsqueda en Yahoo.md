# Obtener las descripciones de los resultados de una búsqueda en Yahoo
## PowerShell, Web scraping 
### URL: https://www.jesusninoc.com/2015/12/23/obtener-las-descripciones-de-los-resultados-de-una-busqueda-en-yahoo/
```PowerShell
$url='https://es.search.yahoo.com/search?p=powershell'
$result = Invoke-WebRequest $url
$result.AllElements | Where Class -eq “lh-18 ” | %{$_.innerText}

```
