# Últimos dominios indexados
## PowerShell, Servers, Web scraping 
### URL: https://www.jesusninoc.com/2016/02/23/ultimos-dominios-indexados/
```PowerShell
(((Invoke-WebRequest 'https://es.wsdata.co/2016-02-22/domains-list.html').AllElements).where{$_.class -eq "responsive"}).innerHTML  -split '[\r\n]' |%{if($_ -match 'href'){$_ -replace "<.*?>"}}

```
