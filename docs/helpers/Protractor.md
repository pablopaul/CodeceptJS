# Protractor

[lib/helper/Protractor.js:48-232](https://github.com/Codeception/CodeceptJS/blob/f6289b7fd02f0b8e74ae11eca0dd10ea271b0763/lib/helper/Protractor.js#L48-L232 "Source code on GitHub")

**Extends SeleniumWebdriver**

Protractor helper is based on [Protractor library](http://www.protractortest.org) and used for testing AngularJS applications.

#### Selenium Installation

1.  Download [Selenium Server](http://docs.seleniumhq.org/download/)
2.  Launch the daemon: `java -jar selenium-server-standalone-2.xx.xxx.jar`

#### PhantomJS Installation

PhantomJS is a headless alternative to Selenium Server that implements [the WebDriver protocol](https://code.google.com/p/selenium/wiki/JsonWireProtocol).
It allows you to run Selenium tests on a server without a GUI installed.

1.  Download [PhantomJS](http://phantomjs.org/download.html)
2.  Run PhantomJS in WebDriver mode: `phantomjs --webdriver=4444`

### Configuration

This helper should be configured in codecept.json

-   `url` - base url of website to be tested
-   `browser` - browser in which perform testing
-   `driver` - which protrator driver to use (local, direct, session, hosted, sauce, browserstack). By default set to 'hosted' which requires selenium server to be started.
-   `seleniumAddress` - Selenium address to connect (default: <http://localhost:4444/wd/hub>)

other options are the same as in [Protractor config](https://github.com/angular/protractor/blob/master/docs/referenceConf.js).

## amInsideAngularApp

[lib/helper/Protractor.js:158-171](https://github.com/Codeception/CodeceptJS/blob/f6289b7fd02f0b8e74ae11eca0dd10ea271b0763/lib/helper/Protractor.js#L158-L171 "Source code on GitHub")

Enters Angular mode (switched on by default)
Should be used after "amOutsideAngularApp"

## amOutsideAngularApp

[lib/helper/Protractor.js:147-152](https://github.com/Codeception/CodeceptJS/blob/f6289b7fd02f0b8e74ae11eca0dd10ea271b0763/lib/helper/Protractor.js#L147-L152 "Source code on GitHub")

Switch to non-Angular mode,
start using WebDriver instead of Protractor in this session

## waitForClickable

[lib/helper/Protractor.js:185-189](https://github.com/Codeception/CodeceptJS/blob/f6289b7fd02f0b8e74ae11eca0dd10ea271b0763/lib/helper/Protractor.js#L185-L189 "Source code on GitHub")

Waits for element to become clickable for number of seconds.

**Parameters**

-   `locator`  
-   `sec`  

## waitForElement

[lib/helper/Protractor.js:176-180](https://github.com/Codeception/CodeceptJS/blob/f6289b7fd02f0b8e74ae11eca0dd10ea271b0763/lib/helper/Protractor.js#L176-L180 "Source code on GitHub")

 Waits for element to be present on page (by default waits for 1sec).
 Element can be located by CSS or XPath.
 
**Parameters**

-   `locator`  
-   `sec`  

## waitForText

[lib/helper/Protractor.js:203-210](https://github.com/Codeception/CodeceptJS/blob/f6289b7fd02f0b8e74ae11eca0dd10ea271b0763/lib/helper/Protractor.js#L203-L210 "Source code on GitHub")

Waits for a text to appear (by default waits for 1sec).
Element can be located by CSS or XPath.
Narrow down search results by providing context.

```js
I.waitForText('Thank you, form has been submitted');
I.waitForText('Thank you, form has been submitted', 5, '#modal');
```

**Parameters**

-   `text`  
-   `sec`  
-   `context`  

## waitForVisible

[lib/helper/Protractor.js:194-198](https://github.com/Codeception/CodeceptJS/blob/f6289b7fd02f0b8e74ae11eca0dd10ea271b0763/lib/helper/Protractor.js#L194-L198 "Source code on GitHub")

Waits for an element to become visible on a page (by default waits for 1sec).
Element can be located by CSS or XPath.

**Parameters**

-   `locator`  
-   `sec`  

# Protractor_InheritedMethods

[lib/helper/Protractor.js:412-578](https://github.com/Codeception/CodeceptJS/blob/f6289b7fd02f0b8e74ae11eca0dd10ea271b0763/lib/helper/Protractor.js#L412-L578 "Source code on GitHub")

**Extends SeleniumWebdriver**

Methods below are inherited from SeleniumWebdriver helper,
in a similar manner as Protractor is extending SeleniumWebdriverJS.

## amOnPage

[lib/helper/Protractor.js:417-417](https://github.com/Codeception/CodeceptJS/blob/f6289b7fd02f0b8e74ae11eca0dd10ea271b0763/lib/helper/Protractor.js#L417-L417 "Source code on GitHub")

Opens a web page in a browser. Requires relative or absolute url.
If url starts with `/`, opens a web page of a site defined in `url` config parameter.

```js
I.amOnPage('/'); // opens main page of website
I.amOnPage('https://github.com'); // opens github
I.amOnPage('/login'); // opens a login page
```

## appendField

[lib/helper/Protractor.js:421-421](https://github.com/Codeception/CodeceptJS/blob/f6289b7fd02f0b8e74ae11eca0dd10ea271b0763/lib/helper/Protractor.js#L421-L421 "Source code on GitHub")

Appends text to a input field or textarea.
Field is located by name, label, CSS or XPath

```js
I.appendField('#myTextField', 'appended');
```

## attachFile

[lib/helper/Protractor.js:425-425](https://github.com/Codeception/CodeceptJS/blob/f6289b7fd02f0b8e74ae11eca0dd10ea271b0763/lib/helper/Protractor.js#L425-L425 "Source code on GitHub")

Attaches a file to element located by label, name, CSS or XPath
Path to file is relative current codecept directory (where codecept.json is located).
File will be uploaded to remove system (if tests are running remotely).

```js
I.attachFile('Avatar', 'data/avatar.jpg');
I.attachFile('form input[name=avatar]', 'data/avatar.jpg');
```

## checkOption

[lib/helper/Protractor.js:429-429](https://github.com/Codeception/CodeceptJS/blob/f6289b7fd02f0b8e74ae11eca0dd10ea271b0763/lib/helper/Protractor.js#L429-L429 "Source code on GitHub")

Selects a checkbox or radio button.
Element is located by label or name or CSS or XPath.

The second parameter is a context (CSS or XPath locator) to narrow the search.

```js
I.checkOption('#agree');
I.checkOption('I Agree to Terms and Conditions');
I.checkOption('agree', '//form');
```

## clearCookie

[lib/helper/Protractor.js:433-433](https://github.com/Codeception/CodeceptJS/blob/f6289b7fd02f0b8e74ae11eca0dd10ea271b0763/lib/helper/Protractor.js#L433-L433 "Source code on GitHub")

Clears a cookie by name,
if none provided clears all cookies

```js
I.clearCookie();
I.clearCookie('test');
```

## click

[lib/helper/Protractor.js:437-437](https://github.com/Codeception/CodeceptJS/blob/f6289b7fd02f0b8e74ae11eca0dd10ea271b0763/lib/helper/Protractor.js#L437-L437 "Source code on GitHub")

Perform a click on a link or a button, given by a locator.
If a fuzzy locator is given, the page will be searched for a button, link, or image matching the locator string.
For buttons, the "value" attribute, "name" attribute, and inner text are searched. For links, the link text is searched.
For images, the "alt" attribute and inner text of any parent links are searched.

The second parameter is a context (CSS or XPath locator) to narrow the search.

```js
// simple link
I.click('Logout');
// button of form
I.click('Submit');
// CSS button
I.click('#form input[type=submit]');
// XPath
I.click('//form/*[@type=submit]');
// link in context
I.click('Logout', '#nav');
// using strict locator
I.click({css: 'nav a.login'});
```

## dontSee

[lib/helper/Protractor.js:473-473](https://github.com/Codeception/CodeceptJS/blob/f6289b7fd02f0b8e74ae11eca0dd10ea271b0763/lib/helper/Protractor.js#L473-L473 "Source code on GitHub")

Opposite to `see`. Checks that a text is not present on a page.
Use context parameter to narrow down the search.

```js
I.dontSee('Login'); // assume we are already logged in
```

## dontSeeCheckboxIsChecked

[lib/helper/Protractor.js:441-441](https://github.com/Codeception/CodeceptJS/blob/f6289b7fd02f0b8e74ae11eca0dd10ea271b0763/lib/helper/Protractor.js#L441-L441 "Source code on GitHub")

 Verifies that the specified checkbox is not checked.
 
## dontSeeCookie

[lib/helper/Protractor.js:445-445](https://github.com/Codeception/CodeceptJS/blob/f6289b7fd02f0b8e74ae11eca0dd10ea271b0763/lib/helper/Protractor.js#L445-L445 "Source code on GitHub")

Checks that cookie with given name does not exist.

## dontSeeCurrentUrlEquals

[lib/helper/Protractor.js:449-449](https://github.com/Codeception/CodeceptJS/blob/f6289b7fd02f0b8e74ae11eca0dd10ea271b0763/lib/helper/Protractor.js#L449-L449 "Source code on GitHub")

Checks that current url is not equal to provided one.
If a relative url provided, a configured url will be prepended to it.

## dontSeeElement

[lib/helper/Protractor.js:453-453](https://github.com/Codeception/CodeceptJS/blob/f6289b7fd02f0b8e74ae11eca0dd10ea271b0763/lib/helper/Protractor.js#L453-L453 "Source code on GitHub")

Opposite to `seeElement`. Checks that element is not visible

## dontSeeInCurrentUrl

[lib/helper/Protractor.js:457-457](https://github.com/Codeception/CodeceptJS/blob/f6289b7fd02f0b8e74ae11eca0dd10ea271b0763/lib/helper/Protractor.js#L457-L457 "Source code on GitHub")

Checks that current url does not contain a provided fragment.

## dontSeeInField

[lib/helper/Protractor.js:461-461](https://github.com/Codeception/CodeceptJS/blob/f6289b7fd02f0b8e74ae11eca0dd10ea271b0763/lib/helper/Protractor.js#L461-L461 "Source code on GitHub")

Checks that value of input field or textare doesn't equal to given value
Opposite to `seeInField`.

## dontSeeInSource

[lib/helper/Protractor.js:465-465](https://github.com/Codeception/CodeceptJS/blob/f6289b7fd02f0b8e74ae11eca0dd10ea271b0763/lib/helper/Protractor.js#L465-L465 "Source code on GitHub")

Checks that the current page contains the given string in its raw source code
## dontSeeInTitle

[lib/helper/Protractor.js:469-469](https://github.com/Codeception/CodeceptJS/blob/f6289b7fd02f0b8e74ae11eca0dd10ea271b0763/lib/helper/Protractor.js#L469-L469 "Source code on GitHub")

Checks that title does not contain text.
## executeAsyncScript

[lib/helper/Protractor.js:477-477](https://github.com/Codeception/CodeceptJS/blob/f6289b7fd02f0b8e74ae11eca0dd10ea271b0763/lib/helper/Protractor.js#L477-L477 "Source code on GitHub")

Executes async script on page.
Provided function should execute a passed callback (as first argument) to signal it is finished.

## executeScript

[lib/helper/Protractor.js:481-481](https://github.com/Codeception/CodeceptJS/blob/f6289b7fd02f0b8e74ae11eca0dd10ea271b0763/lib/helper/Protractor.js#L481-L481 "Source code on GitHub")

Executes sync script on a page.
Pass arguments to function as additional parameters.
Will return execution result to a test.
In this case you should use generator and yield to receive results.

## fillField

[lib/helper/Protractor.js:485-485](https://github.com/Codeception/CodeceptJS/blob/f6289b7fd02f0b8e74ae11eca0dd10ea271b0763/lib/helper/Protractor.js#L485-L485 "Source code on GitHub")

Fills a text field or textarea with the given string.
Field is located by name, label, CSS, or XPath.

```js
// by label
I.fillField('Email', 'hello@world.com');
// by name
I.fillField('password', '123456');
// by CSS
I.fillField('form#login input[name=username]', 'John');
// or by strict locator
I.fillField({css: 'form#login input[name=username]'}, 'John');
```

## grabAttributeFrom

[lib/helper/Protractor.js:489-489](https://github.com/Codeception/CodeceptJS/blob/f6289b7fd02f0b8e74ae11eca0dd10ea271b0763/lib/helper/Protractor.js#L489-L489 "Source code on GitHub")

Retrieves an attribute from an element located by CSS or XPath and returns it to test.
Resumes test execution, so **should be used inside a generator with `yield`** operator.

```js
let hint = yield I.grabAttributeFrom('#tooltip', 'title');
```

## grabCookie

[lib/helper/Protractor.js:493-493](https://github.com/Codeception/CodeceptJS/blob/f6289b7fd02f0b8e74ae11eca0dd10ea271b0763/lib/helper/Protractor.js#L493-L493 "Source code on GitHub")

Gets a cookie object by name
* Resumes test execution, so **should be used inside a generator with `yield`** operator.

```js
let cookie = I.grabCookie('auth');
assert(cookie.value, '123456');
```
## grabTextFrom

[lib/helper/Protractor.js:497-497](https://github.com/Codeception/CodeceptJS/blob/f6289b7fd02f0b8e74ae11eca0dd10ea271b0763/lib/helper/Protractor.js#L497-L497 "Source code on GitHub")

Retrieves a text from an element located by CSS or XPath and returns it to test.
Resumes test execution, so **should be used inside a generator with `yield`** operator.

```js
let pin = yield I.grabTextFrom('#pin');
```

## grabTitle

[lib/helper/Protractor.js:501-501](https://github.com/Codeception/CodeceptJS/blob/f6289b7fd02f0b8e74ae11eca0dd10ea271b0763/lib/helper/Protractor.js#L501-L501 "Source code on GitHub")

Retrieves a page title and returns it to test.
Resumes test execution, so **should be used inside a generator with `yield`** operator.

```js
let title = yield I.grabTitle();
```

## grabValueFrom

[lib/helper/Protractor.js:505-505](https://github.com/Codeception/CodeceptJS/blob/f6289b7fd02f0b8e74ae11eca0dd10ea271b0763/lib/helper/Protractor.js#L505-L505 "Source code on GitHub")

Retrieves a value from a form element located by CSS or XPath and returns it to test.
Resumes test execution, so **should be used inside a generator with `yield`** operator.

```js
let email = yield I.grabValueFrom('input[name=email]');
```

## pressKey

[lib/helper/Protractor.js:509-509](https://github.com/Codeception/CodeceptJS/blob/f6289b7fd02f0b8e74ae11eca0dd10ea271b0763/lib/helper/Protractor.js#L509-L509 "Source code on GitHub")

Presses a key on a focused element.
Speical keys like 'Enter', 'Control', [etc](https://code.google.com/p/selenium/wiki/JsonWireProtocol#/session/:sessionId/element/:id/value)
will be replaced with corresponding unicode.
If modiferier key is used (Control, Command, Alt, Shift) in array, it will be released afterwards.
```js
I.pressKey('Enter');
I.pressKey(['Control','a']);
```

## resizeWindow

[lib/helper/Protractor.js:513-513](https://github.com/Codeception/CodeceptJS/blob/f6289b7fd02f0b8e74ae11eca0dd10ea271b0763/lib/helper/Protractor.js#L513-L513 "Source code on GitHub")

Resize the current window to provided width and height.
First parameter can be set to `maximize`

## saveScreenshot

[lib/helper/Protractor.js:517-517](https://github.com/Codeception/CodeceptJS/blob/f6289b7fd02f0b8e74ae11eca0dd10ea271b0763/lib/helper/Protractor.js#L517-L517 "Source code on GitHub")

Saves a screenshot to ouput folder (set in codecept.json).
Filename is relative to output folder.

```js
I.saveScreenshot('debug.png');
```

## see

[lib/helper/Protractor.js:553-553](https://github.com/Codeception/CodeceptJS/blob/f6289b7fd02f0b8e74ae11eca0dd10ea271b0763/lib/helper/Protractor.js#L553-L553 "Source code on GitHub")

Checks that a page contains a visible text.
Use context parameter to narrow down the search.

```js
I.see('Welcome'); // text welcome on a page
I.see('Welcome', '.content'); // text inside .content div
I.see('Register', {css: 'form.register'}); // use strict locator
```

## seeCheckboxIsChecked

[lib/helper/Protractor.js:521-521](https://github.com/Codeception/CodeceptJS/blob/f6289b7fd02f0b8e74ae11eca0dd10ea271b0763/lib/helper/Protractor.js#L521-L521 "Source code on GitHub")

Verifies that the specified checkbox is checked.

```js
I.seeCheckboxIsChecked('Agree');
I.seeCheckboxIsChecked('#agree'); // I suppose user agreed to terms
I.seeCheckboxIsChecked({css: '#signup_form input[type=checkbox]'});
```

## seeCookie

[lib/helper/Protractor.js:525-525](https://github.com/Codeception/CodeceptJS/blob/f6289b7fd02f0b8e74ae11eca0dd10ea271b0763/lib/helper/Protractor.js#L525-L525 "Source code on GitHub")

Checks that cookie with given name exists.

```js
I.seeCookie('Auth');
```
## seeCurrentUrlEquals

[lib/helper/Protractor.js:529-529](https://github.com/Codeception/CodeceptJS/blob/f6289b7fd02f0b8e74ae11eca0dd10ea271b0763/lib/helper/Protractor.js#L529-L529 "Source code on GitHub")

Checks that current url is equal to provided one.
If a relative url provided, a configured url will be prepended to it.
So both examples will work:

```js
I.seeCurrentUrlEquals('/register');
I.seeCurrentUrlEquals('http://my.site.com/register');
```

## seeElement

[lib/helper/Protractor.js:533-533](https://github.com/Codeception/CodeceptJS/blob/f6289b7fd02f0b8e74ae11eca0dd10ea271b0763/lib/helper/Protractor.js#L533-L533 "Source code on GitHub")

Checks that a given Element is visible
Element is located by CSS or XPath.

```js
I.seeElement('#modal');
```

## seeInCurrentUrl

[lib/helper/Protractor.js:537-537](https://github.com/Codeception/CodeceptJS/blob/f6289b7fd02f0b8e74ae11eca0dd10ea271b0763/lib/helper/Protractor.js#L537-L537 "Source code on GitHub")

Checks that current url contains a provided fragment.

```js
I.seeInCurrentUrl('/register'); // we are on registration page
```

## seeInField

[lib/helper/Protractor.js:541-541](https://github.com/Codeception/CodeceptJS/blob/f6289b7fd02f0b8e74ae11eca0dd10ea271b0763/lib/helper/Protractor.js#L541-L541 "Source code on GitHub")

Checks that the given input field or textarea equals to given value.
For fuzzy locators, fields are matched by label text, the "name" attribute, CSS, and XPath.

```js
I.seeInField('Username', 'davert');
I.seeInField({css: 'form textarea'},'Type your comment here');
I.seeInField('form input[type=hidden]','hidden_value');
I.seeInField('#searchform input','Search');
```

## seeInSource

[lib/helper/Protractor.js:545-545](https://github.com/Codeception/CodeceptJS/blob/f6289b7fd02f0b8e74ae11eca0dd10ea271b0763/lib/helper/Protractor.js#L545-L545 "Source code on GitHub")

Checks that the current page contains the given string in its raw source code.

```js
I.seeInSource('<h1>Green eggs &amp; ham</h1>');
```

## seeInTitle

[lib/helper/Protractor.js:549-549](https://github.com/Codeception/CodeceptJS/blob/f6289b7fd02f0b8e74ae11eca0dd10ea271b0763/lib/helper/Protractor.js#L549-L549 "Source code on GitHub")

Checks that title contains text.

## selectOption

[lib/helper/Protractor.js:557-557](https://github.com/Codeception/CodeceptJS/blob/f6289b7fd02f0b8e74ae11eca0dd10ea271b0763/lib/helper/Protractor.js#L557-L557 "Source code on GitHub")

Selects an option in a drop-down select.
Field is siearched by label | name | CSS | XPath.
Option is selected by visible text or by value.

```js
I.selectOption('Choose Plan', 'Monthly'); // select by label
I.selectOption('subscription', 'Monthly'); // match option by text
I.selectOption('subscription', '0'); // or by value
I.selectOption('//form/select[@name=account]','Permium');
I.selectOption('form select[name=account]', 'Premium');
I.selectOption({css: 'form select[name=account]'}, 'Premium');
```

Provide an array for the second argument to select multiple options.

```js
I.selectOption('Which OS do you use?', ['Andriod', 'OSX']);
```

## setCookie

[lib/helper/Protractor.js:561-561](https://github.com/Codeception/CodeceptJS/blob/f6289b7fd02f0b8e74ae11eca0dd10ea271b0763/lib/helper/Protractor.js#L561-L561 "Source code on GitHub")

Sets a cookie

```js
I.setCookie({name: 'auth', value: true});
```
## waitForElement

[lib/helper/Protractor.js:565-565](https://github.com/Codeception/CodeceptJS/blob/f6289b7fd02f0b8e74ae11eca0dd10ea271b0763/lib/helper/Protractor.js#L565-L565 "Source code on GitHub")

 Waits for element to be present on page (by default waits for 1sec).
 Element can be located by CSS or XPath.
 
## waitForEnabled

[lib/helper/Protractor.js:569-569](https://github.com/Codeception/CodeceptJS/blob/f6289b7fd02f0b8e74ae11eca0dd10ea271b0763/lib/helper/Protractor.js#L569-L569 "Source code on GitHub")

Waits for element to become enabled (by default waits for 1sec).
Element can be located by CSS or XPath.

## waitForText

[lib/helper/Protractor.js:573-573](https://github.com/Codeception/CodeceptJS/blob/f6289b7fd02f0b8e74ae11eca0dd10ea271b0763/lib/helper/Protractor.js#L573-L573 "Source code on GitHub")

Waits for a text to appear (by default waits for 1sec).
Element can be located by CSS or XPath.
Narrow down search results by providing context.

```js
I.waitForText('Thank you, form has been submitted');
I.waitForText('Thank you, form has been submitted', 5, '#modal');
```

## waitForVisible

[lib/helper/Protractor.js:577-577](https://github.com/Codeception/CodeceptJS/blob/f6289b7fd02f0b8e74ae11eca0dd10ea271b0763/lib/helper/Protractor.js#L577-L577 "Source code on GitHub")

Waits for an element to become visible on a page (by default waits for 1sec).
Element can be located by CSS or XPath.