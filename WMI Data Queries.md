# WMI Data Queries
## PowerShell, Processes, Services 
### URL: https://www.jesusninoc.com/2015/02/20/wmi-data-queries/
```PowerShell
$query = "SELECT * FROM Win32_Service"
Get-WMIObject -Query $query

```
```PowerShell
$query = "SELECT * FROM Win32_Service WHERE Name='EFS'"
Get-WMIObject -Query $query

```
