# Detectar la búsqueda sobre instalaciones de phpMyAdmin en logs
## Logs, PHP, Security, Servers 
### URL: https://www.jesusninoc.com/2009/05/03/detectar-la-busqueda-sobre-instalaciones-de-phpmyadmin-en-logs/
```PowerShell
15:01:21 W3SVC1 0.0.0.0 GET /phpMyAdmin/main.php - 80 - 0.0.0.0 - 404 0 3
15:01:21 W3SVC1 0.0.0.0 GET /main.php - 80 - 0.0.0.0 - 404 0 2
15:01:21 W3SVC1 0.0.0.0 GET /php/main.php - 80 - 0.0.0.0 - 404 0 3
15:01:21 W3SVC1 0.0.0.0 GET /PMA/main.php - 80 - 0.0.0.0 - 404 0 3
15:01:21 W3SVC1 0.0.0.0 GET /phpmyadmin/main.php - 80 - 0.0.0.0 - 404 0 3
15:01:21 W3SVC1 0.0.0.0 GET /phpmyadmin2/main.php - 80 - 0.0.0.0 - 404 0 3
15:01:21 W3SVC1 0.0.0.0 GET /db/main.php - 80 - 0.0.0.0 - 404 0 3
15:01:21 W3SVC1 0.0.0.0 GET /mysql/main.php - 80 - 0.0.0.0 - 404 0 3
15:01:21 W3SVC1 0.0.0.0 GET /myadmin/main.php - 80 - 0.0.0.0 - 404 0 3
15:03:24 W3SVC1 0.0.0.0 GET /phpmyadmin/main.php - 80 - 0.0.0.0 - 404 0 3
15:03:24 W3SVC1 0.0.0.0 GET /phpMyAdmin/main.php - 80 - 0.0.0.0 - 404 0 3
15:03:24 W3SVC1 0.0.0.0 GET /myadmin/main.php - 80 - 0.0.0.0 - 404 0 3

```
