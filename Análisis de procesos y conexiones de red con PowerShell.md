# Análisis de procesos y conexiones de red con PowerShell
## Network, PowerShell, Processes, Services 
### URL: https://www.jesusninoc.com/2016/07/11/analisis-de-procesos-y-conexiones-de-red-con-powershell/
```PowerShell
Get-Process | select cpu,id,name | sort cpu -Descending

```
```PowerShell
(Get-WmiObject win32_process) | Select-Object Processid,Name,CommandLine

```
```PowerShell
foreach($conex in @(netstat -ano))
{
    foreach($proceso in ps | where id -EQ 900)
    {
        if($conex -match $proceso.Id -and $proceso.Id -ne 4 -and $proceso.Id -ne 0)
        {
            write-host $conex “-PROCESO->” $proceso.Name $proceso.Id
        }
    }
}

```
```PowerShell
netstat -ano | Select-String 900

```
```PowerShell
$baseURL = 'https://whois.arin.net/rest'
$ip = '131.253.14.153'
$url = "$baseUrl/ip/$ip"
$r = Invoke-RestMethod  $url
$r.net.name

```
