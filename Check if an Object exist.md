# Check if an Object exist
## PowerShell 
### URL: https://www.jesusninoc.com/2014/12/26/check-object-exist/
```PowerShell
Get-Content F:\logs\20141215-access.log | %{
$result=$_ | Select-String "404"
if($result -ne $null)
{
$result.ToString().Split(' ')[6]
}
}

```
