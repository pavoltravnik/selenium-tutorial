# Selenium on Windows
Simple guide how to run selenium on Windows machine

### Install Chrome browser
[https://www.google.com/chrome/](https://www.google.com/chrome/)


### Install Python
[https://www.python.org/downloads/](https://www.python.org/downloads/)


### Install Java - OpenJDK
1. Download OpenJDK from [https://jdk.java.net/11/](https://jdk.java.net/11/)
2. Unzip file
3. Create Java folder - C:\Program Files\Java
4. Move jdk-11 folder to C:\Program Files\Java
5. Add environment variable path - Java & Python
![environment variable edit](https://raw.githubusercontent.com/pavoltravnik/selenium-tutorial/master/environment-variable.png)

### Install selenium for python
Open cmd and run:

`python -m pip install --upgrade pip`

`python -m pip install selenium`


### Download Selenium driver for Chrome
Official page of Selenium driver for Chrome [https://sites.google.com/a/chromium.org/chromedriver/](https://sites.google.com/a/chromium.org/chromedriver/)

Direct link - [https://chromedriver.storage.googleapis.com/index.html?path=2.42/](https://chromedriver.storage.googleapis.com/index.html?path=2.42/)


### Getting started with selenium - Documentation
[https://selenium-python.readthedocs.io/getting-started.html](https://selenium-python.readthedocs.io/getting-started.html)

```python
import time
from selenium import webdriver

driver = webdriver.Chrome('C:/Users/tester/Downloads/chromedriver.exe')
driver.get('http://www.google.com/xhtml');
time.sleep(5)
search_box = driver.find_element_by_name('q')
search_box.send_keys('ChromeDriver')
search_box.submit()
time.sleep(5)
driver.quit()
```

### Download Selenium Standalone Server 3.14.0
[https://www.seleniumhq.org/download/](https://www.seleniumhq.org/download/)


### How to use
[https://github.com/SeleniumHQ/selenium/wiki/Grid2](https://github.com/SeleniumHQ/selenium/wiki/Grid2)

Open cmd:

`java -jar selenium-server-standalone-3.14.0.jar -role hub`

`java -jar selenium-server-standalone-3.14.0.jar -role node  -hub http://localhost:4444/grid/register`
