# Select files between two dates and copy them
## Filesystem, PowerShell 
### URL: https://www.jesusninoc.com/2014/03/12/select-files-between-two-dates-and-copy-them/
```PowerShell
#Select files between two dates and copy - Backup
Get-Childitem F:\power\files | ? {$_.LastAccessTime -le (get-date).adddays(-1) -and $_.LastAccessTime -ge (get-date).adddays(-2) } | % {copy $_.Fullname c:\backup}

```
