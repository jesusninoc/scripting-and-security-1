# MD5 File Hash
## Cryptography, PowerShell, Security 
### URL: https://www.jesusninoc.com/2013/01/02/md5-file-hash/
```PowerShell
$LiteralPath="wpncore.dll"
$file = get-item -literalpath $LiteralPath
$Provider = new-object System.Security.Cryptography.MD5CryptoServiceProvider
$stringbuilder = new-object System.Text.StringBuilder
$stream = $file.OpenRead()
$a=$Provider.ComputeHash($stream) | % {$stringbuilder.Append($_.ToString("X2"))}
$stringbuilder.ToString()

```
