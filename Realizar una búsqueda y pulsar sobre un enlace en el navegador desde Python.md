# Realizar una búsqueda y pulsar sobre un enlace en el navegador desde Python
## Automation, Python 
### URL: https://www.jesusninoc.com/2016/05/03/realizar-una-busqueda-y-pulsar-sobre-un-enlace-en-el-navegador-desde-python/
```Python
from selenium import webdriver
from selenium.webdriver.common.keys import Keys
browser = webdriver.Firefox()
browser.implicitly_wait(10)
browser.get('https://www.google.es')
findElem = browser.find_element_by_id('lst-ib')
findElem.send_keys('Python')
findElem.send_keys(Keys.RETURN)
findElem = browser.find_element_by_link_text('Welcome to Python.org')
findElem.click()

```
