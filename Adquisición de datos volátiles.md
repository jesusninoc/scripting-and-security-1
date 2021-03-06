# Adquisición de datos volátiles
## Forensic analysis, Network, PowerShell 
### URL: https://www.jesusninoc.com/2016/02/06/adquisicion-de-datos-volatiles/
```PowerShell
#Información sobre procesos
Get-Process | Select-Object Name,Path,Company,CPU,Product,TotalProcessorTime,StartTime

#Información sobre hilos
(Get-Process chrome | Select-Object Threads).Threads
Get-Process | select -expand Threads

#Información sobre conexiones
#https://www.jesusninoc.com/2015/11/13/cmdlets-for-tcpip-model-layers/
Get-NetAdapterHardwareInfo
Get-NetAdapter -Physical
Get-NetNeighbor
Get-NetAdapterStatistics
Get-NetAdapter | Select-Object Name,MacAddress
Get-NetAdapter | Select-Object Name,MacAddress
Get-WmiObject -Class Win32_NetworkAdapterConfiguration | Select-Object Description,MACAddress
Get-NetAdapter | Select-Object Name,MacAddress
Get-WmiObject -Class Win32_NetworkAdapterConfiguration | Select-Object Description,MACAddress
((Get-NetAdapterBinding).DisplayName) -match 'Protocolo de Internet'
(Get-NetIPInterface) | Select-Object InterfaceAlias,AddressFamily
Get-NetIPv4Protocol
Get-NetIPv6Protocol
Get-NetRoute
Get-NetNat
Get-NetNatExternalAddress
Get-NetNatGlobal
Get-NetNatSession
Get-NetNatStaticMapping
Get-NetNatTransitionConfiguration
Get-NetNatTransitionMonitoring
Get-NetFirewallAddressFilter
Get-NetFirewallApplicationFilter
Get-NetFirewallInterfaceFilter
Get-NetFirewallInterfaceTypeFilter
Get-NetFirewallPortFilter
Get-NetFirewallProfile
Get-NetFirewallRule
Get-NetFirewallSecurityFilter
Get-NetFirewallServiceFilter
Get-NetFirewallSetting
Get-NetTCPSetting
Get-NetTCPConnection
Get-NetTCPConnection | Select-Object LocalPort,Remoteport
Get-NetUDPSetting
Get-NetUDPEndpoint
(Get-NetUDPEndpoint).LocalPort
Get-DnsClient
Get-DnsClientCache
Get-DnsClientGlobalSetting
Get-DnsClientNrptGlobal
Get-DnsClientNrptPolicy
Get-DnsClientNrptRule
Get-DnsClientServerAddress

#Fecha y hora del sistema
Get-Date

#Última hora de arranque del sistema
Get-CimInstance -ClassName win32_operatingsystem | select csname, lastbootuptime
Get-WmiObject win32_operatingsystem | select csname, @{LABEL='LastBootUpTime';EXPRESSION={$_.ConverttoDateTime($_.lastbootuptime)}}

#DLL
Get-Process | select -expand MainModule
Get-Process | select -expand Modules

```
