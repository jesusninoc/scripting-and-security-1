# Leer de un fichero direcciones URL y extraer información de cada URL
## PowerShell, Web scraping 
### URL: https://www.jesusninoc.com/2016/01/25/leer-de-un-fichero-direcciones-url-y-extraer-informacion-de-cada-url/
```PowerShell
#Guardar en un fichero las direcciones URL que vamos a recorrer y extraer un elemento
#https://www.tiempo.com/madrid.htm
#https://www.tiempo.com/barcelona.htm
#https://www.tiempo.com/sevilla.htm

gc D:\power\ficherostiempo.txt | % {((Invoke-WebRequest $_).AllElements | Where class -eq 'ddTemp T1Loc color-texto-t100-0' | %{$_.innerText})}

```
