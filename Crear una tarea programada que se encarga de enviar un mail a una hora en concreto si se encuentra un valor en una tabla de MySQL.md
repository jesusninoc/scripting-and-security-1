# Crear una tarea programada que se encarga de enviar un mail a una hora en concreto si se encuentra un valor en una tabla de MySQL
## Database, PowerShell, Schedule tasks 
### URL: https://www.jesusninoc.com/2016/01/27/crear-una-tarea-programa-que-se-encarga-de-enviar-un-mail-a-una-hora-en-concreto-si-se-encuentra-un-valor-en-una-tabla-de-mysql/
```PowerShell
[void][System.Reflection.Assembly]::LoadWithPartialName("MySql.Data")
$Connection = New-Object MySql.Data.MySqlClient.MySqlConnection
$ConnectionString = "server=" + "localhost" + ";port=3306;uid=" + "root" + ";pwd=" + "root" + ";database="+"world"
$Connection.ConnectionString = $ConnectionString
$Connection.Open()

$Query='select name from city'
$Command = New-Object MySql.Data.MySqlClient.MySqlCommand($Query, $Connection)
$DataAdapter = New-Object MySql.Data.MySqlClient.MySqlDataAdapter($Command)
$DataSet = New-Object System.Data.DataSet
$RecordCount = $dataAdapter.Fill($dataSet, "data")

$elemento='Gaza'
$DataSet.Tables[0].Rows.name | %{if($_ | Select-String $elemento)
{
'Existe el elemento en la tabla'
#Utilizar un servidor SMTP por ejemplo https://www.jesusninoc.com/2015/01/12/instalar-hmailserver-imap-smtp-y-pop3/
Send-MailMessage -to "mail2@example.com" -from “mail@example.com” -subject "Existe el elemento en la tabla" -SmtpServer localhost -Body $elemento
}
}

$Connection.Close()

```
```PowerShell
$action=New-ScheduledTaskAction -Execute 'Powershell.exe' -Argument '-NoProfile -WindowStyle Hidden -command D:\mysqlmail.ps1'
$trigger=New-ScheduledTaskTrigger -Daily -At 9am
Register-ScheduledTask -Action $action -Trigger $trigger -TaskName "TareaProgramada" -Description "Comprobación de valor"

```
