# ImageMagick Convert Command-Line Tool
## Graphics, PHP, PowerShell 
### URL: https://www.jesusninoc.com/2015/02/07/imagemagick-convert-command-line-tool/
```PowerShell
https://www.imagemagick.org/script/binary-releases.php#windows

```
```PowerShell
cd ‘C:\Program Files\ImageMagick-6.9.0-Q16’
$fichero='F:\power\SampleImages\01.jpg'
$ficheroout=’F:\power\01corregido.jpg’
.\convert.exe $fichero -resize 360x100 -quality 95 -brightness-contrast 45 -auto-gamma -median 4 $ficheroout

```
