# List computers using net view and compare the MAC
## Network, PowerShell 
### URL: https://www.jesusninoc.com/2014/05/29/list-computers-using-net-view-compare-mac/
```PowerShell
function Get-NetView
{
switch -regex (NET.EXE VIEW)
{
"^\\(?<Name>S+)s+"
{
$matches.Name
}
}
}

foreach($i in Get-NetView)
{
(get-wmiobject -class "Win32_NetworkAdapterConfiguration" -computername $i).MACAddress
}

```
