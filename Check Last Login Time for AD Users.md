# Check Last Login Time for AD Users
## PowerShell 
### URL: https://www.jesusninoc.com/2014/05/06/check-last-login-time-ad-users/
```PowerShell
Get-ADUser -Filter 'Name -like "*user*"' | %{
($_ | Get-ADObject -Properties lastLogon).lastlogon
$dt = [DateTime]::FromFileTime(($_ | Get-ADObject -Properties lastLogon).lastlogon)
Write-Host $_ "last logged on at:" $dt
}

```
