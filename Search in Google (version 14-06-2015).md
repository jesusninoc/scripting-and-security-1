# Search in Google (version 14-06-2015)
## Automation, PowerShell 
### URL: https://www.jesusninoc.com/2015/06/14/search-in-google-version-14-06-2015/
```PowerShell
$MouseEventSig=@’
[DllImport('user32.dll',CharSet=CharSet.Auto, CallingConvention=CallingConvention.StdCall)]
public static extern void mouse_event(long dwFlags, long dx, long dy, long cButtons, long dwExtraInfo);
‘@

$IE= New-Object -com InternetExplorer.Application
$IE.navigate2(“https://www.google.es”)

while ($IE.busy) {
Start-Sleep -milliseconds 100
}

Start-Sleep -milliseconds 100

$IE.visible=$true
$IE.Document.getElementById(“lst-ib”).value=”PowerShell”

Start-Sleep -milliseconds 1000

$MouseEvent = Add-Type -memberDefinition $MouseEventSig -name 'MouseEventWinApi' -passThru

#Position TextBox Google Search in IE
#[System.Windows.Forms.Cursor]::Position = New-Object System.Drawing.Point(755,382)
[System.Windows.Forms.Cursor]::Position = New-Object System.Drawing.Point(882,461)
$MouseEvent::mouse_event(0x00000002, 0, 0, 0, 0)
$MouseEvent::mouse_event(0x00000004, 0, 0, 0, 0)

```
