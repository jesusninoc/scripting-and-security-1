# Abrir un puerto en el firewall de Windows
## Network 
### URL: https://www.jesusninoc.com/2015/03/01/abrir-un-puerto-en-el-firewall-de-windows/
```PowerShell
netsh advfirewall firewall add rule name="Programa TCP 87" dir=in action=allow protocol=TCP localport=87

```
