# Last Longon Time and Display Name in Exchange Online
## PowerShell 
### URL: https://www.jesusninoc.com/2014/11/12/last-longon-time-display-name-exchange-online/
```PowerShell
#Important
#Necessary: Microsoft Online Services Sign-In Assistant for IT Professionals RTW
#The Microsoft Online Services Sign-In Assistant provides end user sign-in capabilities to Microsoft Online Services, such as Office 365.
#Link: https://www.microsoft.com/en-gb/download/details.aspx?id=28177
#If you have problems with MSOnline: MSOnline can't be imported on PowerShell (Connect-MsolService error)

#Connect to Exchange Online
Import-Module MSOnline
Get-Module
$O365Cred = Get-Credential
$O365Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://pod50248psh.outlook.com/powershell-liveid?PSVersion=4.0 -Credential $O365Cred -Authentication Basic -AllowRedirection
Import-PSSession $O365Session
Connect-MsolService –Credential $O365Cred

#Last Longon Time and Display Name in Exchange Online
$mail = (Get-Mailbox | Get-MailboxStatistics)

#Save information and convert to CSV
$mail | Select-Object DisplayName, LastLogonTime | ConvertTo-Csv | Out-File F:\fich.csv

```
