# Pulsar sobre un enlace de la segunda página de los resultados de una búsqueda desde Python
## Python 
### URL: https://www.jesusninoc.com/2016/05/15/pulsar-sobre-un-enlace-de-la-segunda-pagina-de-los-resultados-de-una-busqueda-desde-python/
```Python
from selenium import webdriver
from selenium.webdriver.common.keys import Keys
import time
browser = webdriver.Firefox()
browser.implicitly_wait(10)
browser.get('https://www.google.es')
findElem = browser.find_element_by_id('lst-ib')
findElem.send_keys('Python')
findElem.send_keys(Keys.RETURN)
findElem = browser.find_element_by_link_text('2')
findElem.send_keys(Keys.RETURN)
time.sleep(5)
findElem = browser.find_element_by_link_text('Python - Reddit')
findElem.click()

```
