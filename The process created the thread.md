# The process created the thread
## PowerShell, Processes, Threads 
### URL: https://www.jesusninoc.com/2015/04/15/the-process-created-the-thread/
```PowerShell
(Get-WmiObject -Class Win32_Thread).ProcessHandle | %{
Get-Process -Id $_
}

```
```PowerShell
(Get-WmiObject -Class Win32_Thread).ProcessHandle | %{Get-Process -Id $_} | Group-Object

```
