# Abrir direcciones web en Safari leyendo de un fichero y hacer clic en un enlace de cada web abierta
## AppleScript, Automation, Web 
### URL: https://www.jesusninoc.com/2016/01/29/abrir-direcciones-web-en-safari-leyendo-de-un-fichero-y-hacer-clic-en-un-enlace-de-cada-web-abierta/
```AppleScript
set direcciones to paragraphs of (read POSIX file "/Users/lamac/Desktop/file.txt")
repeat with linea in direcciones
	tell application "Safari"
		open location linea
		activate
	end tell
	delay 10
	activate application "Safari"
	tell application "System Events"
		tell process "Safari"
			clic at {865, 262}
		end tell
	end tell
	delay 10
end repeat

```
