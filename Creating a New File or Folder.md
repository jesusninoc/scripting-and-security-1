# Creating a New File or Folder
## Filesystem, PowerShell 
### URL: https://www.jesusninoc.com/2014/11/16/creating-new-file-folder/
```PowerShell
New-Item c:\scripts\Windows PowerShell -ItemType directory

```
```PowerShell
New-Item c:\scripts\new_file.txt -ItemType file

```
```PowerShell
New-Item : The file 'C:\scripts\new_file.txt' already exists.

```
```PowerShell
New-Item c:\scripts\new_file.txt -ItemType file -force

```
```PowerShell
New-Item c:\scripts\new_file.txt -ItemType file -force -value "This is text added to the file"

```
