# How to draw the letter T
## Graphics, PowerShell 
### URL: https://www.jesusninoc.com/2013/02/22/how-to-draw-the-letter-t/
```PowerShell
#Create pen
$mypen = new-object Drawing.Pen red
$mypen.width = 10

$form = New-Object Windows.Forms.Form
$form.Width = 500
$form.Height = 550
$formGraphics = $form.createGraphics()

#T
$form.add_paint({$formGraphics.DrawLine($mypen, 0, 0, 200, 0)})

$form.add_paint({$formGraphics.DrawLine($mypen, 100, 0, 100, 200)})

$form.ShowDialog()

```
