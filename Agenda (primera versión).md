# Agenda (primera versión)
## PowerShell 
### URL: https://www.jesusninoc.com/2014/04/27/agenda-primera-version/
```PowerShell
#Para leer los datos que se van a almacenar en la "Agenda (primera versión)" hay que utilizar "Leer agenda (primera versión)"
#https://www.jesusninoc.com/2014/04/28/leer-agenda-primera-version/

do
{
Write-Host "------------------------------------------------------"
Write-Host "Agenda"
$nombre=Read-Host "Introduzca nombre: "
$dni=Read-Host "Introduzca DNI: "
$edad=Read-Host "Introduzca edad: "
$nombre,$dni,$edad > $dni".txt"
$control=Read-Host "¿Quiere continuar introduciendo datos (1 para sí y 0 para no)?"
}while($control -eq 1)

```
