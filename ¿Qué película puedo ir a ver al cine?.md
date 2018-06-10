# ¿Qué película puedo ir a ver al cine?
## Automation, Multimedia, PowerShell, Web scraping 
### URL: https://www.jesusninoc.com/2015/12/08/que-pelicula-puedo-ir-a-ver-al-cine/
```PowerShell
$url='https://www.youtube.com/user/UniversalSpain/playlists?sort=lad&flow=list&view=1'
$result = Invoke-WebRequest $url
#Respetar los dos espacios entre "link yt"
$result.AllElements | Where class -eq “ spf-link  yt-uix-sessionlink” | %{$_.outerText
'https://www.youtube.com'+$_.href}
```
