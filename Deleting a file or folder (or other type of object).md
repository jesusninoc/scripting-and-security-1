# Deleting a file or folder (or other type of object)
## Filesystem, PowerShell 
### URL: https://www.jesusninoc.com/2014/11/21/deleting-a-file-or-folder-or-other-type-of-object/
```PowerShell
Remove-Item c:\scripts\test.txt

```
```PowerShell
Remove-Item c:\scripts\*

```
```PowerShell
Confirm
The item at C:\test\scripts has children and the -recurse parameter was not specified. 
If you continue, all children will be removed with the item. Are you sure you want to continue?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help
(default is "Y"):

```
```PowerShell
Remove-Item c:\scripts\* -recurse

```
```PowerShell
Remove-Item c:\scripts\* -exclude *.wav

```
```PowerShell
Remove-Item c:\scripts\* -include .wav,.mp3

```
```PowerShell
Remove-Item c:\scripts\* -include *.txt -exclude *test*

```
```PowerShell
Remove-Item c:\scripts\*.vbs -whatif

```
```PowerShell
What if: Performing operation "Remove File" on Target "C:\scripts\imapi.vbs".
What if: Performing operation "Remove File" on Target "C:\scripts\imapi2.vbs".
What if: Performing operation "Remove File" on Target "C:\scripts\methods.vbs".
What if: Performing operation "Remove File" on Target "C:\scripts\read-write.vbs".
What if: Performing operation "Remove File" on Target "C:\scripts\test.vbs".
What if: Performing operation "Remove File" on Target "C:\scripts\winsat.vbs".

```
```PowerShell
Remove-Item alias:\show

```
```PowerShell
Set-Location env:\

```
