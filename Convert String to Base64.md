# Convert String to Base64
## PowerShell 
### URL: https://www.jesusninoc.com/2015/10/03/convert-string-to-base64/
```PowerShell
[System.Convert]::ToBase64String([System.Text.Encoding]::UTF8.GetBytes('hola'))

```
