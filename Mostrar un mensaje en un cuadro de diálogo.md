# Mostrar un mensaje en un cuadro de diálogo
## PowerShell, Visual Basic 
### URL: https://www.jesusninoc.com/2016/04/10/mostrar-un-mensaje-en-un-cuadro-de-dialogo-2/
```PowerShell
#https://msdn.microsoft.com/en-us/library/microsoft.visualbasic.interaction.msgbox(v=vs.110).aspx

Add-Type -AssemblyName Microsoft.VisualBasic

$message='Mensaje de prueba'
$title='Título de prueba'

[Microsoft.VisualBasic.Interaction]::MsgBox($message,01,$title)

```
# Mostrar un mensaje en un cuadro de diálogo
## PowerShell, Visual Basic 
### URL: https://www.jesusninoc.com/2016/02/02/mostrar-un-mensaje-en-un-cuadro-de-dialogo/
```PowerShell
#https://msdn.microsoft.com/es-es/library/6z0ak68w(v=vs.90).aspx

Add-Type -AssemblyName Microsoft.VisualBasic

$message='Mensaje de prueba'
$title='Título de prueba'
$textodefecto='Texto por defecto'

[Microsoft.VisualBasic.Interaction]::InputBox($message,$title,$textodefecto, 100, 100)

```
