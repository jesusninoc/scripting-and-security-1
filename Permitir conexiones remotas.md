# Permitir conexiones remotas
## PowerShell, Registry 
### URL: https://www.jesusninoc.com/2016/05/08/permitir-conexiones-remotas/
```PowerShell
cd HKLM:\
$RegKey ='HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Terminal Server\'
Set-ItemProperty -Path $RegKey -Name fDenyTSConnections -Value 0

```
