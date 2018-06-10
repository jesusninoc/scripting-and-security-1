# ¿Qué actualizaciones de seguridad tenemos aplicadas en Windows y para qué sirven?
## PowerShell, Security, Updates 
### URL: https://www.jesusninoc.com/2015/04/12/que-actualizaciones-de-seguridad-tenemos-aplicadas-en-windows-y-para-que-sirven/
```PowerShell
#Seleccionar los identificadores de las actualizaciones de seguridad (HotFixID)
foreach($kb in (Get-HotFix | Select-Object HotFixID))
{
[String]$texto=''

#Componer URL con el valor HotFixID
$url='https://www.bing.com/search?q='+$kb.hotfixid
#Hacer petición al buscador Bing para analizar la información sobre la actualización de seguridad
$result=Invoke-WebRequest $url

#Analizar los datos devueltos por el buscador
foreach($linea in ($result.AllElements | Where class -eq 'b_caption').outerText)
{
#Marcar en los resultados obtenidos los identificadores de las actualizaciones de seguridad (HotFixID)
#-----------------------------------------------------------------------
#-----------------------------------------------------------------------
$linea.Split(' ') | % {
if($_ | Select-String $kb.hotfixid)
{
Write-Host $_ ' ' -BackgroundColor Cyan -ForegroundColor Blue -NoNewline
}
else
{
Write-Host $_ ' ' -NoNewline
}
}
Write-Host ' '
}
#-----------------------------------------------------------------------
#-----------------------------------------------------------------------
}

```
