# Searching IP addresses in text files
## Network, PowerShell, Registry 
### URL: https://www.jesusninoc.com/2014/11/24/searching-ip-addresses-in-text-files/
```PowerShell
Write-Host "IP addresses:`n"
Get-ChildItem C:\Users\ -rec -ea SilentlyContinue | ForEach-Object {
Select-String "\b\d{1,3}\.\d{1,3}\.\d{1,3}\.\d{1,3}\b" -input (Get-ItemProperty -Path $_.PsPath) -AllMatches | ForEach-Object {($_.matches)|Select-Object Value}
}

```
