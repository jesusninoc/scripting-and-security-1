# Comprobar si una cuenta de correo electrónico ha sido comprometida en alguna fuga de datos (versión 2)
## PowerShell, Security, Web 
### URL: https://www.jesusninoc.com/2016/06/17/comprobar-si-una-cuenta-de-correo-electronico-ha-sido-comprometida-en-alguna-fuga-de-datos-version-2/
```PowerShell
$mail='example@hotmail.com'
try{
 #Con Invoke-WebRequest da error al cargar el certificado, mejor descargar el fichero JSON resultado
 Start-BitsTransfer "https://haveibeenpwned.com/api/v2/breachedaccount/$mail" -Destination resultado.txt
 "Cuenta comprometida"
 "La cuenta ha sido comprometida en: "
 gc .\resultado.txt | ConvertFrom-JSON
}
catch
{
 if($_.Exception.Response.StatusCode.Value__ -eq 404)
 {
 "Cuenta no comprometida"
 }
}

```
