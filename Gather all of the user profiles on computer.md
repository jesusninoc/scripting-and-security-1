# Gather all of the user profiles on computer
## PowerShell 
### URL: https://www.jesusninoc.com/2015/03/05/gather-user-profiles-computer/
```PowerShell
Get-WmiObject -ComputerName . Win32_UserProfile -filter "LocalPath Like 'C:\\Users\\%'" -ea stop

```
