# Ejemplo de utilización de WordPress JSON API
## PowerShell 
### URL: https://www.jesusninoc.com/2016/01/11/ejemplo-de-utilizacion-de-wordpress-json-api/
```PowerShell
(((Invoke-WebRequest -Uri 'https://es.wordpress.org/wp-json/oembed/1.0/embed?url=https://es.wordpress.org/2016/01/01/resumen-del-2015/').content | ConvertFrom-JSON).html) | Out-File D:\power\fichero.html
Start-Process chrome D:\power\fichero.html

```
