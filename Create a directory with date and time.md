# Create a directory with date and time
## Filesystem, PowerShell 
### URL: https://www.jesusninoc.com/2014/02/26/create-a-directory-with-date-and-time/
```PowerShell
New-Item -ItemType Directory -Path F:\power\powershell -Name (Get-Date).tostring("dd-MM-yyyy-hh-mm-ss")

```
