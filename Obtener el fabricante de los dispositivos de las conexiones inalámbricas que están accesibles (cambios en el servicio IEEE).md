# Obtener el fabricante de los dispositivos de las conexiones inalámbricas que están accesibles (cambios en el servicio IEEE)
## Database, Network, PowerShell, Web, Wireless 
### URL: https://www.jesusninoc.com/2016/01/24/obtener-el-fabricante-de-los-dispositivos-de-las-conexiones-inalambricas-que-estan-accesibles-cambios-en-el-servicio-ieee/
```PowerShell
$macwifi=netsh wlan show networks mode=bssid | Select-String '([0-9A-F]{2}[:]){5}([0-9A-F]{2})$' | % {$_.matches} | Select-Object value

#Descargar el fichero que contiene información sobre los fabricantes
#IEEE offers Registration Authority programs or registries which maintain lists of unique identifiers under standards and issue unique identifiers to those wishing to register them.
Start-BitsTransfer https://standards-oui.ieee.org/oui.txt -Destination D:\power\oui.txt
$fichero=gc D:\power\oui.txt

foreach($mac in $macwifi.value)
{
$mac.ToUpper()
$fichero | Select-String ($mac.Substring(0,8).replace(':','')).ToUpper()
}

```
```PowerShell
$macwifi=netsh wlan show networks mode=bssid | Select-String '([0-9A-F]{2}[:]){5}([0-9A-F]{2})$' | % {$_.matches} | Select-Object value

foreach($mac in $macwifi.value)
{
$mac
$url=”https://services13.ieee.org/RST/standards-ra-web/rest/assignments/download/?registry=MA-L&amp;format=html&amp;text=”+$mac.Substring(0,8).replace(':','')
$url
$result=''
Start-Sleep -Seconds 10
$result=Invoke-WebRequest $url
#Here are the results of your search through the public section of the IEEE Standards MA-L database report for MAC
($result.AllElements | Where tagName -eq “PRE”).outerText
}

```
