# Escanear puertos con Python
## Network, Python 
### URL: https://www.jesusninoc.com/2017/02/04/escanear-puertos-con-python/
```Python
import socket
for port in range(80,90):
 s=socket.socket(socket.AF_INET, socket.SOCK_STREAM)
 result=s.connect_ex(("www.jesusninoc.com",port))
 if result == 0:
 print("Puerto abierto")
 else:
 print("Puerto no abierto")
 s.close()

```
