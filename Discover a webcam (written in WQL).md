# Discover a webcam (written in WQL)
## Hardware, PowerShell 
### URL: https://www.jesusninoc.com/2015/11/16/discover-a-webcam-written-in-wql/
```PowerShell
Get-WmiObject -query "select * from Win32_PnPEntity where caption like '%cam%'"

```
