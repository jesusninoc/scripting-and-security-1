# Mostrar los cargos directivos de una empresa
## PowerShell, Web, Web scraping 
### URL: https://www.jesusninoc.com/2016/01/04/mostrar-los-cargos-directivos-de-una-empresa/
```PowerShell
$web=Invoke-WebRequest 'https://www.empresia.es/empresa/google-spain/'
$web.AllElements | Where id -eq “ListaRelaciones” | %{$_.innertext}

```
