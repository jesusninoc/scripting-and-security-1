# Contar el número de usuarios que hay en el sistema
## PowerShell, Users 
### URL: https://www.jesusninoc.com/2016/07/15/contar-el-numero-de-usuarios-que-hay-en-el-sistema/
```PowerShell
(Get-WmiObject Win32_UserAccount | Select-Object Name).count

```
