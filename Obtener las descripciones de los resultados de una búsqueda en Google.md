# Obtener las descripciones de los resultados de una búsqueda en Google
## PowerShell, Web scraping 
### URL: https://www.jesusninoc.com/2015/12/03/obtener-las-descripciones-de-los-resultados-de-una-busqueda-en-google/
```PowerShell
$url='https://www.google.es/search?q=jesusninoc'
$result = Invoke-WebRequest $url
$result.AllElements | Where Class -eq “st” | %{$_.innerText}

```
