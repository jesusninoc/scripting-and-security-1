# Clonar permisos NTFS
## Filesystem, Permissions, PowerShell 
### URL: https://www.jesusninoc.com/2015/01/23/clonar-permisos-ntfs/
```PowerShell
$Origen = 'F:\power\carpeta1'
$Destino = 'F:\power\carpeta2'
$PermisosOrigen = Get-Acl -Path $Origen
Set-Acl -Path $Destino -AclObject $PermisosOrigen

```
