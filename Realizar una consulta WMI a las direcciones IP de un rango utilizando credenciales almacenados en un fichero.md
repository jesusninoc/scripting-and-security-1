# Realizar una consulta WMI a las direcciones IP de un rango utilizando credenciales almacenados en un fichero
## PowerShell, Security 
### URL: https://www.jesusninoc.com/2016/08/21/realizar-una-consulta-wmi-a-las-direcciones-ip-de-un-rango-utilizando-credenciales-almacenados-en-un-fichero/
```PowerShell
$credenciales=Import-Clixml -Path credenciales.xml
1..254 | %{
Get-WmiObject -Class Win32_BIOS -ComputerName ('192.168.1.'+$_) -Credential $credenciales
}

```
