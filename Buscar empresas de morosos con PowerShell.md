# Buscar empresas de morosos con PowerShell
## PowerShell, Web, Web scraping 
### URL: https://www.jesusninoc.com/2016/06/30/buscar-empresas-de-morosos-con-powershell/
```PowerShell
$nombremoroso='apellidos y nombre del muy moroso'
$nombremorososinespacios=$nombremoroso.Replace(' ','-')
$urlmoroso='https://www.empresia.es/persona/'+$nombremorososinespacios

$web=Invoke-WebRequest $urlmoroso
$web.AllElements | Where id -eq “ListaRelaciones” | %{$_.innertext}

```
