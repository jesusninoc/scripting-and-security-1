# Send information between server and clients (read web, encrypt and create HTML)
## Cryptography, Network, PowerShell, Security, Servers, Web 
### URL: https://www.jesusninoc.com/2014/04/16/send-information-between-server-and-clients-read-web-encrypt-and-create-html/
```PowerShell
#############################
##Server
#############################

#Port server: 5219
$port='5219'

try
{
$Message=''
$endpoint = new-object System.Net.IPEndPoint([ipaddress]::any,$port)
$listener = new-object System.Net.Sockets.TcpListener $EndPoint
$listener.start()
$data = $listener.AcceptTcpClient() # will block here until connection
$bytes = New-Object System.Byte[] 1024
$stream = $data.GetStream()

while (($i = $stream.Read($bytes,0,$bytes.Length)) -ne 0)
{
$EncodedText = New-Object System.Text.ASCIIEncoding
$data = $EncodedText.GetString($bytes,0, $i)
}

$stream.close()
$listener.stop()
}catch [exception]{}

#Simple algorithm to decipher (Convert number of vowels)
for ($i=0; $i -lt $data.Length; $i++)
{
switch ($data[$i])
{
'1' {$Message += 'a'}
'2' {$Message += 'e'}
'3' {$Message += 'i'}
'4' {$Message += 'o'}
'5' {$Message += 'u'}
default {$Message += $data[$i]}
}
}

#Save message
#$Message | Out-File F:\power\html\preba.html
$string='Content: ' +$Message+'' | Out-File F:\power\html\preba.html

```
```PowerShell
#############################
##Client
#############################

$UTF8 = [System.Text.Encoding]::UTF8
$IP = [System.Net.Dns]::GetHostAddresses('127.0.0.1')
$Message=''

#Read web
$rootDir = 'https://www.jesusninoc.com/'
$contenido = Invoke-WebRequest($rootDir)
$webpagetxt = ‘F:\power\html\prueba.txt’ #Directory save HTML

Start-Sleep 5
$contenido=$contenido.AllElements.innerText

#Connect to port 5219
$Address = [System.Net.IPAddress]::Parse($IP)
$Socket = New-Object System.Net.Sockets.TCPClient($Address,5219)

#Simple algorithm to encrypt (Convert vowels in numbers)
for ($i=0; $i -lt $contenido.Length; $i++)
{
switch ($contenido[$i])
{
'a' {$Message += '1'}
'e' {$Message += '2'}
'i' {$Message += '3'}
'o' {$Message += '4'}
'u' {$Message += '5'}
default {$Message += $contenido[$i]}
}
}

$data = $UTF8.GetBytes($Message)

$Stream = $Socket.GetStream()
$Writer = New-Object System.IO.StreamWriter($Stream)

$Message | %{
$Writer.WriteLine($_)
$Writer.Flush()
}

$Stream.Close()
$Socket.Close()

```
