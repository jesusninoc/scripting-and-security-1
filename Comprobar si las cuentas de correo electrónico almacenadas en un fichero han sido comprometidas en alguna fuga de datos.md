# Comprobar si las cuentas de correo electrónico almacenadas en un fichero han sido comprometidas en alguna fuga de datos
## PowerShell, Security, Web 
### URL: https://www.jesusninoc.com/2016/06/18/comprobar-si-las-cuentas-de-correo-electronico-almacenadas-en-un-fichero-han-sido-comprometidas-en-alguna-fuga-de-datos/
```PowerShell
gc ficheromails.txt | %{
$_
    try{
        #Con Invoke-WebRequest da error al cargar el certificado, mejor descargar el fichero JSON resultado
        Start-BitsTransfer "https://haveibeenpwned.com/api/breachedaccount/$_" -Destination resultado.txt
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
}

```
