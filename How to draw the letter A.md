# How to draw the letter A
## Graphics, PowerShell 
### URL: https://www.jesusninoc.com/2012/02/01/how-to-draw-the-letter-a/
```PowerShell
#Create pen
$mypen = new-object Drawing.Pen red
$mypen.width = 10

#Create Form
$form = New-Object Windows.Forms.Form
$form.Width = 500
$form.Height = 550
$formGraphics = $form.createGraphics()

#A
$form.add_paint({$formGraphics.DrawLine($mypen, 0, 0, 200, 0)})
$form.add_paint({$formGraphics.DrawLine($mypen, 0, 100, 200, 100)})

$form.add_paint({$formGraphics.DrawLine($mypen, 0, 0, 0, 200)})
$form.add_paint({$formGraphics.DrawLine($mypen, 200, 0, 200, 200)})

$form.ShowDialog()

```
