# Drawing number one
## Graphics 
### URL: https://www.jesusninoc.com/2014/04/03/drawing-number-one/
```PowerShell
#Number one

#Create pen
$mypen = new-object Drawing.Pen red
$mypen.width = 10

$form = New-Object Windows.Forms.Form
$formGraphics = $form.createGraphics()

#Drawing perpendicular line
#10,10
#|
#|
#|
#|
#|
#|
#|
#10,200

#Create coordinates of points that define line
#Draw line to screen
$form.add_paint({$formGraphics.DrawLine($mypen, 10, 10, 10, 200)})
$form.ShowDialog()

```
