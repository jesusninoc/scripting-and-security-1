# Guardar el estado de un script y pararlo si la batería es baja
## PowerShell 
### URL: https://www.jesusninoc.com/2016/07/13/guardar-el-estado-de-un-script-y-pararlo-si-la-bateria-es-baja/
```PowerShell
while($true)
{
    if((Get-WmiObject Win32_Battery).EstimatedChargeRemaining -lt 66)
    {
        #Si la batería es menor de 66 hay que guardar estado y parar el script
        "Guardar estado" | Out-File d:\estado.txt
        break
    }
    else
    {
        #Realizar operaciones si la batería es mayor de 66
        Get-Process
    }
    Start-Sleep -Seconds 10
}

```
