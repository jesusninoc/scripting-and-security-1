# Server and client (Sockets UDP)
## Network, PowerShell, Servers 
### URL: https://www.jesusninoc.com/2012/12/29/server-and-client/
```PowerShell
##Server
$port=2020
$endpoint = new-object System.Net.IPEndPoint ([IPAddress]::Any,$port)
$udpclient=new-Object System.Net.Sockets.UdpClient $port
$content=$udpclient.Receive([ref]$endpoint)
[Text.Encoding]::ASCII.GetString($content)
$udpclient.Dispose()

```
```PowerShell
##Client
$port=2020
$endpoint = new-object System.Net.IPEndPoint ([IPAddress]::Loopback,$port)
$udpclient=new-Object System.Net.Sockets.UdpClient
$b=[Text.Encoding]::ASCII.GetBytes('Hi')
$bytesSent=$udpclient.Send($b,$b.length,$endpoint)
$udpclient.Close()

```
