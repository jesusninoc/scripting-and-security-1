# How to draw the letter K
## Graphics, PowerShell 
### URL: https://www.jesusninoc.com/2013/02/15/draw-letter-k/
```PowerShell
#Create pen
$mypen = new-object Drawing.Pen red
$mypen.width = 10

$form = New-Object Windows.Forms.Form
$form.Width = 500
$form.Height = 550
$formGraphics = $form.createGraphics()

#K
$form.add_paint({$formGraphics.DrawLine($mypen, 0, 100, 200, 0)})
$form.add_paint({$formGraphics.DrawLine($mypen, 0, 100, 200, 200)})

$form.add_paint({$formGraphics.DrawLine($mypen, 0, 0, 0, 200)})

$form.ShowDialog()

```
