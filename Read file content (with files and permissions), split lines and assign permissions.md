# Read file content (with files and permissions), split lines and assign permissions
## Bash, Filesystem, Permissions 
### URL: https://www.jesusninoc.com/2014/12/07/read-file-content-files-permissions-split-lines-assign-permissions/
```Shell
while read line
do
chmod `echo $line | cut -d \, -f 2` `echo $line | cut -d \, -f 1`
done < "permisos.txt"

```
