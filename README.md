# alpine-php-node-puppeteer

## install
docker pull dmitry9/alpine-php-node-puppeteer:latest
##### OR
docker pull dmitry9/alpine-php-node-puppeteer:0.0.4

## before usage
you should pass --no-sandbox, --disable-gpu, --disable-dev-shm-usage args when launch browser
```javascript
const puppeteer = require('puppeteer');

(async() => {
    const browser = await puppeteer.launch({
         headless: <bool>,
         ignoreDefaultArgs: ['--enable-automation'], // if you want to avoid detection
         args: ['--no-sandbox', '--disable-gpu', '--disable-dev-shm-usage'],
         executablePath: process.env.CHROME_BIN || null,
    });  
    const page = await browser.newPage();
    await page.goto('https://www.google.com/', {waitUntil: 'networkidle2'});
    browser.close();
})();
```
##  usage
run interactively:
```shell
$ sudo docker container run -it -v /PATH_TO_YOUR_SCRIPT:/app dmitry9/alpine-php-node-puppeteer:0.0.4 sh
```
