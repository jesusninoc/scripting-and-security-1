# Tweets by author
## PowerShell, Web scraping 
### URL: https://www.jesusninoc.com/2016/03/17/tweets-by-author/
```PowerShell
(((Invoke-WebRequest 'https://twitter.com/microsoft').AllElements).where{$_.Class -eq "TweetTextSize TweetTextSize--16px js-tweet-text tweet-text"}).innerText

```
