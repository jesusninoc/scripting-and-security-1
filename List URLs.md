# List URLs
## PowerShell, Web scraping 
### URL: https://www.jesusninoc.com/2012/12/29/list-urls/
```PowerShell
((Invoke-WebRequest "https://www.jesusninoc.com").Links).href

```
