# Listar las carpetas de una cuenta de Outlook
## PowerShell 
### URL: https://www.jesusninoc.com/2015/01/22/listar-las-carpetas-de-una-cuenta-de-outlook/
```PowerShell
Add-Type -Assembly "Microsoft.Office.Interop.Outlook"
$Outlook = New-Object -ComObject Outlook.Application
$Namespace = $Outlook.GetNameSpace("MAPI")
$NameSpace.Folders.Item(6).Folders | FT FolderPath

```
