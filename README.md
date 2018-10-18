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

driver = webdriver.Chrome('C:/Users/tester/Downloads/chromedriver.exe')  # Optional argument, if not specified will search path.
driver.get('http://www.softec.sk');
time.sleep(3) # Let the user actually see something!
search_icon = driver.find_element_by_class_name('icon-search')
search_icon.click()
time.sleep(3) # Let the user actually see something!
search_box = driver.find_element_by_class_name('search-field')
search_box.send_keys('umelá inteligencia')
search_box.submit()
time.sleep(3) # Let the user actually see something!
search_box = driver.find_element_by_xpath('//h2[1]/a[@title="Umelá inteligencia sa už stáva doménou finančných služieb"]')
driver.close()
driver.quit()
```

### Download Selenium Standalone Server 3.14.0
[https://www.seleniumhq.org/download/](https://www.seleniumhq.org/download/)


### How to use
[https://github.com/SeleniumHQ/selenium/wiki/Grid2](https://github.com/SeleniumHQ/selenium/wiki/Grid2)

Open cmd:

`java -jar selenium-server-standalone-3.14.0.jar -role hub`

`java -jar selenium-server-standalone-3.14.0.jar -role node  -hub http://localhost:4444/grid/register`


## Puppeteer

Puppeteer is a Node library which provides a high-level API to control Chrome or Chromium over the DevTools Protocol. Puppeteer runs headless by default, but can be configured to run full (non-headless) Chrome or Chromium.

Official github page - [https://github.com/GoogleChrome/puppeteer](https://github.com/GoogleChrome/puppeteer)

### Install Node.js

[https://nodejs.org/en/](https://nodejs.org/en/)

### Install puppeteer

`npm i puppeteer`

### Example example.js

Create file example.js

```javascript
const puppeteer = require('puppeteer');

(async () => {
  const browser = await puppeteer.launch();
  const page = await browser.newPage();
  await page.setViewport({ width: 1280, height: 800 })
  await page.goto('https://softec.sk');
  await page.waitFor(2000);
  await page.click('#site-navigation > button.search-toggle > span > svg');
  await page.waitFor(2000);
  await page.type('#main-search-form > div > label > input', 'umelá inteligencia', {delay: 100});
  await page.waitFor(2000);
  await page.click('#main-search-form > div > button.search-submit > span > svg');
  await page.screenshot({path: 'softec.png'});
  await browser.close();
})();

```

### Run puppeteer

`node example.js`
