# Añadir el contenido de un fichero a una ArrayList y ordenar los elementos
## PowerShell 
### URL: https://www.jesusninoc.com/2015/08/30/anadir-el-contenido-de-un-fichero-a-una-arraylist-y-ordenar-los-elementos/
```PowerShell
$fichero = Get-Content C:\Users\lam\Desktop\client.txt

#Inicializa una nueva instancia de la clase ArrayList que está vacía y tiene la capacidad inicial predeterminada
[System.Collections.ArrayList] $arraylist = New-Object System.Collections.ArrayList

ForEach ($elemento in $fichero){
#Agrega un objeto al final de ArrayList
[void]$arraylist.Add($elemento)
}

#Número de elementos de ArrayList
$arraylist.Count

#Ordena todos los elementos de ArrayList
$arraylist.Sort()

#Muestra todos los elementos de ArrayList ordenados
$arraylist

```
