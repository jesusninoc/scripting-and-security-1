# Artefactos
## Forensic analysis, PowerShell 
### URL: https://www.jesusninoc.com/2016/02/11/artefactos/
```PowerShell
#Shellbags
#Más información https://digital-forensics.sans.org/blog/2011/07/05/shellbags
Get-ChildItem HKCU:\Software\Microsoft\Windows\Shell
Get-ChildItem HKCU:\Software\Microsoft\Windows\

#Registros HIVE
Get-ChildItem HKLM:\SAM
Get-ChildItem HKLM:\SECURITY
Get-ChildItem HKLM:\SOFTWARE
Get-ChildItem HKLM:\HARDWARE

#Información sobre programas ejecutados (Prefetch)
Get-ChildItem C:\Windows\Prefetch

#Información sobre navegadores
Get-ChildItem C:\Users\user\AppData\Local\Microsoft\Windows\History
Get-ChildItem C:\Users\user\AppData\Local\Mozilla\Firefox\Profiles

#Ficheros temporales
Get-ChildItem C:\Windows\Temp

#Ficheros temporales de los usuarios
Get-ChildItem C:\Users\user\AppData\Local\Temp

#Información sobre el hardware
Get-ChildItem C:\Windows\Inf

#Información sobre USB
Get-ChildItem HKLM:\SYSTEM\ControlSet001\Enum\USB
Get-ChildItem HKLM:\SYSTEM\ControlSet001\Enum\USBSTOR
Get-ChildItem HKLM:\SYSTEM\CurrentControlSet\Enum\USB
Get-ChildItem HKLM:\SYSTEM\CurrentControlSet\Enum\USBSTOR
Get-ChildItem 'HKLM:\SOFTWARE\Microsoft\Windows Portable Devices\Devices'
Get-ChildItem 'HKLM:\SYSTEM\ControlSet001\Control\DeviceClasses'

#Información acerca de las acciones de instalación durante la instalación
Get-Content C:\Windows\setupact.log

#Información sobre los errores de instalación durante la instalación
Get-Content C:\Windows\setuperr.log

```
