# Select name and URL where artist is “XXXX” (Yahoo music) and convert to JSON (YQL statement)
## PowerShell 
### URL: https://www.jesusninoc.com/2013/03/27/select-name-and-url-where-artist-is-xxxx-yahoo-music-and-convert-to-json-yql-statement/
```PowerShell
#Well, it does not work like that

#IMPORTANT
#Console: https://developer.yahoo.com/yql/console/
#YOUR YQL STATEMENT: select * from music.artist.id where ids="289286"
#URL: https://developer.yahoo.com/yql/console/#
#h=select%20*%20from%20music.artist.id%20where%20ids%3D%
#22289286%22

$ur="https://bit.ly/XbKWjG"
#"https://bit.ly/XbKWjG" -> "https://query.yahooapis.com/v1/public/yql?q=
#select%20*%20from%20music.artist.id%20where%20ids%3D%22289286%22&
#format=json&diagnostics=true&callback="

$result=(Invoke-WebRequest -Uri $ur)
$conv=$result.Content
$convi = $conv | ConvertFrom-JSON
$convi.query.results.Artist.name
$convi.query.results.Artist.url

```
