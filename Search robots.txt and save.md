# Search robots.txt and save
## PowerShell, Security, Servers, Web 
### URL: https://www.jesusninoc.com/2014/10/13/search-robots-txt-save/
```PowerShell
#The Web Robots Pages
#https://www.robotstxt.org/
#Web Robots (also known as Web Wanderers, Crawlers, or Spiders), are programs that traverse the Web automatically. #Search engines such as Google use them to index the web content, spammers use them to scan for email addresses, #and they have many other uses.

Get-Content C:\urls.txt | % {
$name=$_.replace('https://www.','')
$name -match '[a-z]+(\.)' | Out-Null; $file=$Matches[0].Replace('.','')
$find='/robots.txt'
$url=$_+$find
Start-BitsTransfer -Source $url -Destination C:\$file.txt
}

```
