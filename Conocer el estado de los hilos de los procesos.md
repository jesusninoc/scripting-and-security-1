# Conocer el estado de los hilos de los procesos
## PowerShell, Processes, Threads 
### URL: https://www.jesusninoc.com/2015/07/24/conocer-el-estado-de-los-hilos-de-los-procesos/
```PowerShell
(Get-WmiObject -Class Win32_Thread) | Select-Object ProcessHandle,ThreadState | Sort-Object ProcessHandle

```
```PowerShell
(Get-Process).Threads | Select-Object Id,ThreadState | Sort-Object Id

```
