# Listar los archivos de un directorio
## C#, Filesystem, PowerShell 
### URL: https://www.jesusninoc.com/2015/09/15/listar-los-archivos-de-un-directorio/
```PowerShell
$CodigoC = @”

public class Listado
{
public static void Main()
{
System.Console.WriteLine("Listado de todos los archivos del directorio:");
System.IO.DirectoryInfo dir = new System.IO.DirectoryInfo(@"F:\power");

foreach (System.IO.FileInfo file in dir.GetFiles("*.*"))
{
System.Console.WriteLine("{0}, {1}", file.Name, file.Length);
}

System.Console.ReadLine();
}
}

“@

#Importante: utilizar las comillas correctamente en la función del Main()

Add-Type -TypeDefinition $CodigoC -ErrorAction SilentlyContinue

[Listado]::Main()

```
