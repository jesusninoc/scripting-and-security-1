# Temperatura máxima en Barcelona para hoy
## PowerShell, Web scraping 
### URL: https://www.jesusninoc.com/2015/06/28/temperatura-maxima-en-barcelona-para-hoy/
```PowerShell
((Invoke-WebRequest 'https://www.tiempo.com/barcelona.htm').AllElements | Where class -eq 'T2Loc changeUnitT color-texto-t90-8' | %{$_.innerText})[0]

```
