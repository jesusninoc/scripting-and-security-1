# Upload files to FTP automatically and save a copy
## Filesystem, PowerShell, Servers 
### URL: https://www.jesusninoc.com/2014/11/13/upload-files-to-ftp-automatically-and-save-a-copy/
```PowerShell
ForEach ($file in gci F:\power\videos){
$file

$ftp=”ftp://user:pass@domain.com/pub/$File”
$webclient = New-Object System.Net.WebClient
$uri = New-Object System.Uri($ftp)
$webclient.UploadFile($uri, $file)

Move-Item $file.Fullname F:\power\copia
$file.FullName | Out-File F:\power\copiados.txt -Append
}

```
