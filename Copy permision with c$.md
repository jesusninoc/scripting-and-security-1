# Copy permision with c$
## Filesystem, PowerShell 
### URL: https://www.jesusninoc.com/2014/02/18/copy-permision-with-c/
```PowerShell
1..200 | ForEach-Object {
$sour="sour"
$dest="\\192.168.1."+$_+"\c$\dest"
get-acl $sour | set-acl -path $dest
}

```
