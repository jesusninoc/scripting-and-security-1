# Abrir Safari desde Finder
## AppleScript 
### URL: https://www.jesusninoc.com/2016/02/12/abrir-safari-desde-finder/
```AppleScript
tell application "Finder"
activate
open application file "Safari" of folder "Applications" of startup disk
end tell

```
