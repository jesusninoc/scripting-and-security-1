# Locate installed Windows Update
## PowerShell, Updates 
### URL: https://www.jesusninoc.com/2014/12/13/locate-installed-windows-update/
```PowerShell
Get-HotFix | Select-Object hotfixid | Select-String "KB2894867"

```
