# Realizar varias búsquedas con Google Chrome en Android leyendo de un fichero y pulsar en un enlace mediante un script en la shell de Android con ADB
## Android, Bash 
### URL: https://www.jesusninoc.com/2016/04/19/realizar-varias-busquedas-con-google-chrome-en-android-leyendo-de-un-fichero-y-pulsar-en-un-enlace-mediante-un-script-en-la-shell-de-android-con-adb/
```Shell
#Contenido de fichero:
#Android|280|820
#Android|280|1385
for url in `cat buscar.txt`
do sleep 5;
am start -n com.android.chrome/com.google.android.apps.chrome.Main -d 'https://www.google.es'
sleep 5;
input tap 101 880
buscar=`echo $url |  cut -d '|' -f1`;
posicionx=`echo $url |  cut -d '|' -f2`;
posiciony=`echo $url |  cut -d '|' -f3`;
input text $buscar;
input keyevent 66;
sleep 5;
input tap $posicionx $posiciony;
done

```
