# Automatizar el análisis de imágenes utilizando “Buscar por imagen” de Google
## Automation, PowerShell, Web 
### URL: https://www.jesusninoc.com/2015/07/12/automatizar-el-analisis-de-imagenes-utilizando-buscar-por-imagen-de-google/
```PowerShell
#Automatizar el análisis de imágenes utilizando "Buscar por imagen" de Google, en donde se hacen búsquedas en Google con una imagen en lugar de utilizar texto
#Cada una de las imágenes que se quieren analizar, se suben en el apartado "Subir una imagen"

#Importar DLL para simular clic del ratón
$MouseEventSig=@'
[DllImport("user32.dll",CharSet=CharSet.Auto, CallingConvention=CallingConvention.StdCall)]
public static extern void mouse_event(long dwFlags, long dx, long dy, long cButtons, long dwExtraInfo);
'@
$MouseEvent = Add-Type -memberDefinition $MouseEventSig -name "MouseEventWinApi" -passThru

#Listar las imágenes que se van a analizar
Get-ChildItem 'F:\power\imagenes\' | %{
#Abrir "Google Imágenes" en Chrome
Start-Process chrome 'https://www.google.es/imghp'
#Esperar a cargar correctamente la página
Start-Sleep -Seconds 5

#Hacer clic en "Buscar por imagen" es muy importante tener en cuenta la resolución de la pantalla en donde se ejecuta el script
[System.Windows.Forms.Cursor]::Position=New-Object System.Drawing.Point(865,388)
$MouseEvent::mouse_event(0x00000002, 0, 0, 0, 0)
$MouseEvent::mouse_event(0x00000004, 0, 0, 0, 0)
#Esperar a cargar correctamente el apartado "Buscar por imagen"
Start-Sleep -Seconds 5
#Hacer clic en la pestaña "Subir una imagen"
[System.Windows.Forms.Cursor]::Position=New-Object System.Drawing.Point(655,491)
$MouseEvent::mouse_event(0x00000002, 0, 0, 0, 0)
$MouseEvent::mouse_event(0x00000004, 0, 0, 0, 0)
#Esperar a cargar correctamente el apartado "Subir una imagen"
Start-Sleep -Seconds 5
#Hacer clic en el botón "Seleccionar archivo"
[System.Windows.Forms.Cursor]::Position=New-Object System.Drawing.Point(463,543)
$MouseEvent::mouse_event(0x00000002, 0, 0, 0, 0)
$MouseEvent::mouse_event(0x00000004, 0, 0, 0, 0)
#Esperar a cargar correctamente el cuadro de diálogo "Abrir"
Start-Sleep -Seconds 5
[System.Windows.Forms.Cursor]::Position=New-Object System.Drawing.Point(338,417)
#Hacer clic en la caja de texto e introducir la ruta de la imagen que va a ser procesada
$MouseEvent::mouse_event(0x00000002, 0, 0, 0, 0)
$MouseEvent::mouse_event(0x00000004, 0, 0, 0, 0)
#Esperar a estar correctamente posicionado en la caja de texto
Start-Sleep -Seconds 5

#Escribir la ruta completa de la imagen
[System.Windows.Forms.SendKeys]::SendWait($_.FullName)
#Una vez que se ha escrito la ruta completa se pulsa a ENTER para indicar a Google que puede analizar la imagen subida
[System.Windows.Forms.SendKeys]::SendWait('{ENTER}')
#Esperar hasta que Google realiza la búsqueda y devuelva los resultados
Start-Sleep -Seconds 10
#Guardar el contenido de la página web con los resultado de la búsqueda
[System.Windows.Forms.SendKeys]::SendWait('^{s}')
#Esperar hasta que se realiza la operación
Start-Sleep -Seconds 10
#Escribir el nombre del archivo con el que guardar el contenido del resultado de búsqueda
[System.Windows.Forms.SendKeys]::SendWait('F:\power\busqueda\buscar')
#Esperar hasta que se realiza la operación
Start-Sleep -Seconds 10
#Pulsar a ENTER para guardar el contenido del fichero
[System.Windows.Forms.SendKeys]::SendWait('{ENTER}')
#Esperar hasta que se realiza la operación de guardar
Start-Sleep -Seconds 10
#Procesar el contenido del fichero almacenando con los datos de la búsqueda, en concreto el apartado "Páginas con imágenes que coinciden con la búsqueda"
#Si hay contenido que coincide se almacena en un nuevo fichero

gc 'F:\power\busqueda\buscar.html' -Encoding UTF8 | %{$_ | Select-String 'coinciden'} | Out-File 'F:\power\busqueda\datosprocesados.html' -Append
}

```
