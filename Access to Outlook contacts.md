# Access to Outlook contacts
## PowerShell, Security 
### URL: https://www.jesusninoc.com/2015/08/01/access-to-outlook-contacts/
```PowerShell
Add-Type -Assembly 'Microsoft.Office.Interop.Outlook'
$Outlook = New-Object -ComObject Outlook.Application
$Namespace = $Outlook.GetNameSpace('MAPI')
$contactObject = $Namespace.GetDefaultFolder([Microsoft.Office.Interop.Outlook.OlDefaultFolders]::olFolderContacts)
$contactList = $contactObject.Items
$contactList | % {$_.Email1Address}

```
```PowerShell
Add-Type -Assembly 'Microsoft.Office.Interop.Outlook'
$Outlook = New-Object -ComObject Outlook.Application
$Namespace = $Outlook.GetNameSpace('MAPI')
$NameSpace.Folders.Item(2).Folders.Item(2).Items | %{$_.SenderEmailAddress}

```
