# Ver motores de rastreo en los logs analizando User-Agent
## Logs, Security, Servers 
### URL: https://www.jesusninoc.com/2009/05/26/ver-motores-de-rastreo-en-los-logs-analizando-user-agent/
```PowerShell
logparser "SELECT [cs(User-Agent)], COUNT(*) AS EXPR1 FROM 'C:WINDOWSsystem32LogFilesW3*' GROUP BY [cs(User-Agent)] ORDER BY [cs(User-Agent)] desc" -i:IISW3C -o:DATAGRID

```
```PowerShell
logparser "SELECT * FROM 'C:WINDOWSsystem32LogFilesW3*' WHERE cs(User-Agent) like '%robotgenius%'" -i:IISW3C -o:DATAGRID

```
