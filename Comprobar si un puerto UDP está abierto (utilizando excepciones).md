# Comprobar si un puerto UDP está abierto (utilizando excepciones)
## Network, PowerShell, Security 
### URL: https://www.jesusninoc.com/2016/01/17/comprobar-si-un-puerto-udp-esta-abierto-utilizando-excepciones/
```PowerShell
#Se utiliza el puerto por lo tanto no se puede abrir un nuevo socket UDP
ForEach($port in 500..5024){
try
{
$udpobject = new-Object system.Net.Sockets.Udpclient($port)
}
catch
{
$port
$_.Exception.Message
}
}

```
