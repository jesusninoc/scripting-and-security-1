# Crear un recurso compartido y asignar permisos al recurso
## Filesystem, Permissions, PowerShell 
### URL: https://www.jesusninoc.com/2015/06/09/crear-un-recurso-compartido-y-asignar-permisos-al-recurso/
```PowerShell
New-SmbShare -Name fso -Path F:\power –FullAccess administrador -ReadAccess Everyone

```
