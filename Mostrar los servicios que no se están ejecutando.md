# Mostrar los servicios que no se están ejecutando
## PowerShell, Processes, Services 
### URL: https://www.jesusninoc.com/2015/10/27/mostrar-los-servicios-que-no-se-estan-ejecutando/
```PowerShell
Get-Service | Where-Object Status -EQ 'Stopped'

```
