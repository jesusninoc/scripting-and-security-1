# Repeat requests
## PowerShell 
### URL: https://www.jesusninoc.com/2013/04/27/repeat-requests/
```PowerShell
for(1){$a=Invoke-WebRequest "https://www.google.com/a";$a.StatusCode}

```
