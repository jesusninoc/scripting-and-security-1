# Almacenar trailers de cine de Youtube en ficheros HTML
## Multimedia, PowerShell, Web scraping 
### URL: https://www.jesusninoc.com/2015/12/19/almacenar-trailers-de-cine-de-youtube-en-ficheros-html/
```PowerShell
$url='https://www.youtube.com/user/UniversalSpain/playlists?sort=lad&flow=list&view=1'
$result = Invoke-WebRequest $url
#Respetar los dos espacios entre "link yt"
$result.AllElements | Where class -eq “ spf-link  yt-uix-sessionlink” | %{
$ficherofin=$_.outerText
$ficherofin=$ficherofin.Substring(0,20)
$ficherofin
$urlfinal='https://www.youtube.com'+$_.href.replace('/watch?v=','/embed/')
$urlfinal=$urlfinal.Replace('&amp;','?')
'<iframe width="560" height="315" src="'+$urlfinal+'" frameborder="0" allowfullscreen></iframe>' | Out-File D:\power\videoss\$ficherofin.html -Append
}

```
