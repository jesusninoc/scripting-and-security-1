# Detectar la herramienta para escanear la red DFind.exe
## Logs, Security, Servers, Web 
### URL: https://www.jesusninoc.com/2009/05/01/detectar-la-herramienta-para-escanear-la-red-dfind-exe/
```PowerShell
D:\DFind.exe -web 192.168.1.35

```
```PowerShell
2009-05-01 18:32:58 192.168.1.36 192.168.1.35 GET /w00tw00t.at.ISC.SANS.DFind:) - 400 - -

```
```PowerShell
SELECT    cs-uri-stem,sc-status
FROM        'C:\W3SVC1\*.*'
where  cs-uri-stem like '%DFind%'
order by sc-status

```
```PowerShell
/w00tw00t.at.ISC.SANS.DFind:);400
/w00tw00t.at.ISC.SANS.DFind:);400
/w00tw00t.at.ISC.SANS.DFind:);400
/w00tw00t.at.ISC.SANS.DFind:);400
/w00tw00t.at.ISC.SANS.DFind:);400
/w00tw00t.at.ISC.SANS.DFind:);400
/w00tw00t.at.ISC.SANS.DFind:);400
/w00tw00t.at.ISC.SANS.DFind:);400

```
