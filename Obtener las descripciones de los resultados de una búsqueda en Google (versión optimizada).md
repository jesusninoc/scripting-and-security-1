# Obtener las descripciones de los resultados de una búsqueda en Google (versión optimizada)
## PowerShell, Web scraping 
### URL: https://www.jesusninoc.com/2016/01/03/obtener-las-descripciones-de-los-resultados-de-una-busqueda-en-google-version-optimizada/
```PowerShell
(((Invoke-WebRequest 'https://www.google.es/search?q=powershell').AllElements).where{$_.Class -eq "st"}).innerText

```
