# Intensidad de las señales de las conexiones inalámbricas que están accesibles
## Network, PowerShell, Wireless 
### URL: https://www.jesusninoc.com/2015/01/18/intensidad-de-las-senales-de-las-conexiones-inalambricas-que-estan-accesibles/
```PowerShell
netsh wlan show networks mode=bssid | Select-String Nombre,SSID,BSSID,Se¤al

```
