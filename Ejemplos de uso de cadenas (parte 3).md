# Ejemplos de uso de cadenas (parte 3)
## PowerShell, Strings 
### URL: https://www.jesusninoc.com/2014/10/01/ejemplos-de-uso-de-cadenas-parte-3/
```PowerShell
$originalText = 'juan*lopez*guerra'
$splitText = [RegEx]::Escape('*')
$originalText -split $splitText

```
```PowerShell
'[Juan , de los Santos ]' -replace '\s{2,}', ' '

```
