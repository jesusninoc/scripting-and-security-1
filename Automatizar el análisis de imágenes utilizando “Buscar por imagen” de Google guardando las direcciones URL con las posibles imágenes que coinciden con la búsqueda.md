# Automatizar el análisis de imágenes utilizando “Buscar por imagen” de Google guardando las direcciones URL con las posibles imágenes que coinciden con la búsqueda
## Automation, PowerShell 
### URL: https://www.jesusninoc.com/2015/07/14/automatizar-el-analisis-de-imagenes-utilizando-buscar-por-imagen-de-google-guardando-las-direcciones-url-con-las-posibles-imagenes-que-coinciden-con-la-busqueda/
```PowerShell
#Más información en: https://www.jesusninoc.com/2015/07/12/automatizar-el-analisis-de-imagenes-utilizando-buscar-por-imagen-de-google/

$MouseEventSig=@'
[DllImport("user32.dll",CharSet=CharSet.Auto, CallingConvention=CallingConvention.StdCall)]
public static extern void mouse_event(long dwFlags, long dx, long dy, long cButtons, long dwExtraInfo);
'@
$MouseEvent = Add-Type -memberDefinition $MouseEventSig -name "MouseEventWinApi" -passThru

Start-Process chrome 'https://www.google.es/imghp'
Start-Sleep -Seconds 5

[System.Windows.Forms.Cursor]::Position=New-Object System.Drawing.Point(865,388)
$MouseEvent::mouse_event(0x00000002, 0, 0, 0, 0)
$MouseEvent::mouse_event(0x00000004, 0, 0, 0, 0)
Start-Sleep -Seconds 5
[System.Windows.Forms.Cursor]::Position=New-Object System.Drawing.Point(655,491)
$MouseEvent::mouse_event(0x00000002, 0, 0, 0, 0)
$MouseEvent::mouse_event(0x00000004, 0, 0, 0, 0)
Start-Sleep -Seconds 5
[System.Windows.Forms.Cursor]::Position=New-Object System.Drawing.Point(463,543)
$MouseEvent::mouse_event(0x00000002, 0, 0, 0, 0)
$MouseEvent::mouse_event(0x00000004, 0, 0, 0, 0)
Start-Sleep -Seconds 5
[System.Windows.Forms.Cursor]::Position=New-Object System.Drawing.Point(338,417)
$MouseEvent::mouse_event(0x00000002, 0, 0, 0, 0)
$MouseEvent::mouse_event(0x00000004, 0, 0, 0, 0)
Start-Sleep -Seconds 5

[System.Windows.Forms.SendKeys]::SendWait('F:\power\imagenes\configurar10.png')
[System.Windows.Forms.SendKeys]::SendWait('{ENTER}')
Start-Sleep -Seconds 10

[System.Windows.Forms.Cursor]::Position=New-Object System.Drawing.Point(150,41)
$MouseEvent::mouse_event(0x00000002, 0, 0, 0, 0)
$MouseEvent::mouse_event(0x00000004, 0, 0, 0, 0)

[System.Windows.Forms.SendKeys]::SendWait('+{END}')
Start-Sleep -Seconds 5
[System.Windows.Forms.SendKeys]::SendWait('^{c}')

Stop-Process -Name chrome
Stop-Process -Name notepad

Start-Process notepad
Start-Sleep -Seconds 10

[System.Windows.Forms.SendKeys]::SendWait('^{v}')
Start-Sleep -Seconds 10
[System.Windows.Forms.SendKeys]::SendWait('^{g}')
Start-Sleep -Seconds 10
[System.Windows.Forms.SendKeys]::SendWait('f:\url')
Start-Sleep -Seconds 10
[System.Windows.Forms.SendKeys]::SendWait('{ENTER}')
Start-Sleep -Seconds 10

gc F:\url.txt

```
