# Gets all processes that have a working set greater than 100 MB
## Memory, PowerShell, Processes 
### URL: https://www.jesusninoc.com/2015/12/01/gets-all-processes-that-have-a-working-set-greater-than-100-mb/
```PowerShell
#WS(K): The size of the working set of the process, in kilobytes. The working set consists of the pages of memory that were recently referenced by the process

@(Get-Process).where{$_.WorkingSet -gt 100MB}
@(Get-Process).where{$_.WS -gt 100MB}

```
