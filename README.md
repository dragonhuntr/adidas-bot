# Adidas Bot

Launches instances of puppeteer browsers to a specified url and notifies you when an adidas cart page is detected.


## Installation
Install [Node.JS](https://nodejs.org/en/download/) and NPM (NPM is included with Node.JS) 

Install [git](https://git-scm.com/downloads)

Clone or download the repository:

```
git clone https://github.com/Joxroxagain/adidas-bruteforcer.git
```
Navigate to the folder to which you downloaded the files.

If you want to use the google login feature, use the chrome extension EditThisCookie to export your google cookies as JSON and enter the output into the file ```cookies.json```

Edit the config file as you wish.

Install the modules with the following:

```
npm install
```

Then run the following commands to start:
```
npm start
```

## Configuration settings
Open the file ```config.json``` and be careful to adhere to the JSON syntax in order to avoid launch errors.

**Launch options:**

**```url```**: The url that the browsers will go to. For yeezy drops, use ```https://www.adidas.com/yeezy```.

**```taskCount```**: The number of browsers that will be launched.

**```region```**: The region that the bot will operate in. Current suported regions are:
```AU, AT, BE, BR, CA, CN, CZ, DK, FI, FR, DE, IE, IT, MX, NL, NZ, PH, PL, RU, SK, ES, SE, GB, US```

**```splashMode```**: Set to "true" for Yeezy releases and other releases with splash pages. Change to 'false' for all other releases. When enabled, this option makes the browsers wait for a cookie called the 'hmac' which indicates that the add to cart (ATC) page has been reached.

**```headless```**: Enables the use of chrome headless which makes all the browsers invisible until the ATC page is detected. Recomended use to to keep this set to false in case something goes wrong and you need to manually add shoes to cart.

**```headlessAfterSplash```**: Enables chrome headless after the shoe has been added to cart. This is currently not recomended in case there are errors during checkout and manual intervention is needed.

**```splashCookieKeyword```**: Sets the keyword that indicates an ATC page. Default is `hmac` and will be changed if necessary.

**```captchaExpected```**: Set this to 'true' if there will be a captcha to solve sometime during the process. In most cases, this will need to be left as 'true' but it can be disabled to test on non-hyped releases. For this option to work, you will need to have set up [<b>2captcha</b>](https://2captcha.com?from=5308824).

**```webdata```**: This option allows the browsers to use the same webdata as your normal chrome installation (information such as your chrome autofill data, bookmarks, and passwords). This is usefull for manual checkout using chrome autofill. The ```enabled``` sub-option enables this feature and the ```path``` sub-option is only used when the bot cannot auto-detect the path to your chrome data (working on Windows 10 but needs testing on Mac and Linux).

**```autoCart```**: This option enables auto-carting of shoes. Due to the constant changes to adidas splash pages, this feature may not always work. I recomend using this only when the status indicator above says that it is working. To enable, set the ```enabled``` sub-option to 'true' and input the sizes that you want to cart into the ```sizes``` sub-option, seperated by commas. The ```PID``` field allows you to enter the product ID of the shoe you want to cart. Although the bot can usually detect the product ID, entering it can prevent failures.

**```twocaptcha```**: This option enables the auto captcha solving feature using the [<b>2captcha</b>](https://2captcha.com?from=5308824) procvider. Enter your api key into the ```apiKey``` field and set the ```enabled``` option to 'true' in order to enable it. **Important**: This must be set up in order for auto carting to work on releases.

**```autoCheckout```**: This options enables auto checkout of a shoe after it has been added to cart. Enable this feature by changing the ```enabled``` sub-option to 'true' and by filling out your correct billing information under the ```data``` sub-option.

**```retryDelay```**: Sets the number of milliseconds to wait before retrying various operations such as auto-carting and auto-checkout.

**```startUpDelayInterval```**: Sets the number of milliseconds to wait between launching browsers. At least a few seconds is recomended because this will prevent IP bans from too much traffic at once.

**```splashDetectionInterval```**: Sets the number of milliseconds to wait between checks for the add to cart (ATC) page. Very low values (under 10) causes extra load on your computer.

**```alerts```**: When enabled, you will recieve a notification when a browser has passed the splash page or when a recaptcha has been discovered.

**```windowHeight```** and **```windowWidth```**: Change these values to set the size (in pixels) of the browsers viewports. 

## Features
- [x] Auto-updating keeps you on the latest release
- [x] Auto add to cart, via speified sizes or random sizes
- [x] Auto checkout via credit card
- [x] Stock monitoring
- [x] Cart page detection and notification system
- [x] Google cookie import for captcha prevention
- [x] Headless mode
- [x] Detection prevention
- [x] Random user-agent
- [x] Autofill via profiles (chrome autofill imported from your bvrowser)
- [x] Delay between browser launches
- [x] Proxies, imported by proxies.txt file in `IP:PORT` format
- [x] Captcha harvesting with 2captcha
- [x] Support for all regions

## TODO 
- [ ] Checkout success/failure detection

## Credits
[<b>bequadro</b>](https://github.com/bequadro/kju) for some code

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details
