# Extraer títulos y enlaces de una lista de reproducción de Yotube
## Automation, Multimedia, PowerShell 
### URL: https://www.jesusninoc.com/2015/12/05/extraer-titulos-y-enlaces-de-una-lista-de-reproduccion-de-yotube/
```PowerShell
$url='https://www.youtube.com/playlist?list=PLoSIOFPSXQoOLkIBDKdDspqXtsdFEFdOV'
$result = Invoke-WebRequest $url
#Respetar los dos espacios entre "link  spf"
$result.AllElements | Where Class -eq “pl-video-title-link yt-uix-tile-link yt-uix-sessionlink  spf-link ” | %{$_.outerText
'https://www.youtube.com'+$_.href}

```
