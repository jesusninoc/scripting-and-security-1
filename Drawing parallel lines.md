# Drawing parallel lines
## Graphics, PowerShell 
### URL: https://www.jesusninoc.com/2014/02/24/drawing-parallel-lines/
```PowerShell
[void] [System.Reflection.Assembly]::LoadWithPartialName(“System.Drawing”)
[void] [System.Reflection.Assembly]::LoadWithPartialName(“System.Windows.Forms”)

$mypen = new-object Drawing.Pen red
$mypen.width = 10
$form = New-Object Windows.Forms.Form
$formGraphics = $form.createGraphics()
$form.add_paint({$formGraphics.DrawLine($mypen, 10, 10, 200, 10)})
$form.add_paint({$formGraphics.DrawLine($mypen, 10, 60, 200, 60)})
$form.add_paint({$formGraphics.DrawLine($mypen, 10, 110, 200, 110)})
$form.add_paint({$formGraphics.DrawLine($mypen, 10, 160, 200, 160)})
$form.ShowDialog()

```
