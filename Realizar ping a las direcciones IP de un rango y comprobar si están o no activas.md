# Realizar ping a las direcciones IP de un rango y comprobar si están o no activas
## Network, PowerShell 
### URL: https://www.jesusninoc.com/2016/09/17/realizar-ping-a-las-direcciones-ip-de-un-rango-y-comprobar-si-estan-o-no-activas/
```PowerShell
1..254 | %{Test-Connection ('192.168.1.'+$_) -Quiet}

```
