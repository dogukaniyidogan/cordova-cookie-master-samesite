Cookie Master
==============

As you may already know, WebViews on Android and iOS platforms do not support regular use of <code>document.cookie</code> for managing the cookies in your app. This plugin allows you to get and set cookie values from your WebView through a simple interface.

## Supported Platforms
* Android
* iOS

## Installing

Install with Cordova CLI

    $ cordova plugin add https://github.com/dogukaniyidogan/cordova-cookie-master-samesite

## Usage
### Get cookie value
```javascript
cookieMaster.getCookieValue('http://<some host>:<some port>', '<cookie name>', function(data) {
  console.log(data.cookieValue);
}, function(error) {
  if (error) {
    console.log('error: ' + error);
  }
});
```
### Set cookie value
```javascript
cookieMaster.setCookieValue('http://<some host>:<some port>', '<cookie name>', '<cookie value>',
    function() {
        console.log('A cookie has been set');
    },
    function(error) {
        console.log('Error setting cookie: '+error);
    },'httponly;SameSite=None;Secure;');
```
The cookie value should be formatted just like a regular <code>document.cookie</code> value.

### Clear all cookies
```javascript
cookieMaster.clearCookies(
    function() {
    console.log('Cookies have been cleared');
    },
    function() {
        console.log('Cookies could not be cleared');
    });
```

## Limitations
* This version has been tested on Android 4.4 ~ 5.1 devices, iOS 7.1 ~ 9 devices. Experience may vary for different OS versions.


## License
This plugin is distributed under the MIT License.

## Thanks to
This plugin is a fork of Edward Gao's "cookie master" plugin which was forked from Kristian Hristov's "cookie master" plugin. This fork is adding partial WKWebView support.

This plugin was inspired by the great work on the CookieMonster plugin by @barrettc
