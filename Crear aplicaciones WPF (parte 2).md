# Crear aplicaciones WPF (parte 2)
## PowerShell 
### URL: https://www.jesusninoc.com/2016/07/09/crear-aplicaciones-wpf-parte-2/
```PowerShell
Add-Type -AssemblyName PresentationFramework
  
$codigoxaml = @'
<Window xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        Title="Mi primer ejemplo WPF" Height="100" Width="300">
    <Grid>
        <TextBlock Text="Hola"
                   HorizontalAlignment="Center"
                   VerticalAlignment="Center"
                   FontSize="20"
                   FontWeight="Bold"/>
    </Grid>
</Window>
'@

$cargar = [System.XML.XMLReader]::Create([System.IO.StringReader]$codigoxaml)
$ventana = [System.Windows.Markup.XAMLReader]::Load($cargar)
$ventana.ShowDialog()

```
