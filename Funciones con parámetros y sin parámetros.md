# Funciones con parámetros y sin parámetros
## PowerShell 
### URL: https://www.jesusninoc.com/2015/10/14/funciones-con-parametros-y-sin-parametros/
```PowerShell
#Función con parámetros
function sumarp($parametro1, $parametro2)
{
return $parametro1+$parametro2
}
#Ejecutar la función:
sumarp 5 4

#Función sin parámetros
function sumar
{
$args[0]+$args[1]
}
#Ejecutar la función:
sumar 5 4

```
