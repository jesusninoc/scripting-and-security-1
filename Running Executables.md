# Running Executables
## PowerShell, Processes 
### URL: https://www.jesusninoc.com/2015/01/13/running-executables/
```PowerShell
netstat -ano

```
```PowerShell
$str = "Get-Process"
Invoke-Expression $str

```
```PowerShell
$scriptblock = {ping host3}
Invoke-Command -scriptblock $scriptblock -computername "host1","host2"

```
```PowerShell
#opens all TXTs in the current directory
Invoke-Item *.txt

```
