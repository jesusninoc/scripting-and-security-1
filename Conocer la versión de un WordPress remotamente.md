# Conocer la versión de un WordPress remotamente
## PowerShell, Security, Web 
### URL: https://www.jesusninoc.com/2016/01/23/conocer-la-version-de-un-wordpress-remotamente/
```PowerShell
#Fichero url.txt con las direcciones URL que hay que analizar para conocer la versión de WordPress
gc D:\power\urls\url.txt | %{$_
$web=(iwr "$_/readme.html")
$web.AllElements | Where id -eq “logo” |%{$_.outerText}
}

```
