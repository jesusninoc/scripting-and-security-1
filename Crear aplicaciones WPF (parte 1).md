# Crear aplicaciones WPF (parte 1)
## PowerShell 
### URL: https://www.jesusninoc.com/2016/07/08/crear-aplicaciones-wpf-parte-1/
```PowerShell
Add-Type -AssemblyName PresentationFramework
  
$codigoxaml = @'
<Window xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        Title="Mi primer ejemplo WPF" Height="100" Width="300">
    <Grid>
        <TextBlock Text="Hola" />
    </Grid>
</Window>
'@

$cargar = [System.XML.XMLReader]::Create([System.IO.StringReader]$codigoxaml)
$ventana = [System.Windows.Markup.XAMLReader]::Load($cargar)
$ventana.ShowDialog()

```
