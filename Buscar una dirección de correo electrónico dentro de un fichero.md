# Buscar una dirección de correo electrónico dentro de un fichero
## PowerShell 
### URL: https://www.jesusninoc.com/2016/06/16/buscar-una-direccion-de-correo-electronico-dentro-de-un-fichero/
```PowerShell
cd D:\ficheros\
ls -Recurse | %{
gc $_ | Select-String "ejemplo@ejemplo.com"
}

```
