<div class="section page content">

<div id="mobile-menu">

<div id="nav-button" class="fa fa-bars fa-2x button">

</div>

</div>

<div id="logo" class="section">

[Express](/){.express}

</div>

<div id="navbar">

-   [Home](/){#home-menu}
-   -   [Getting started](/en/starter/installing.html)
        -   [Installing](/en/starter/installing.html)
        -   [Hello world](/en/starter/hello-world.html)
        -   [Express generator](/en/starter/generator.html)
        -   [Basic routing](/en/starter/basic-routing.html)
        -   [Static files](/en/starter/static-files.html)
        -   [FAQ](/en/starter/faq.html)
-   -   [Guide](/en/guide/routing.html){.active}
        -   [Routing](/en/guide/routing.html)
        -   [Writing middleware](/en/guide/writing-middleware.html)
        -   [Using middleware](/en/guide/using-middleware.html)
        -   [Using template
            engines](/en/guide/using-template-engines.html)
        -   [Error handling](/en/guide/error-handling.html)
        -   [Debugging](/en/guide/debugging.html)
        -   [Express behind proxies](/en/guide/behind-proxies.html)
        -   [Moving to Express 4](/en/guide/migrating-4.html)
        -   [Moving to Express 5](/en/guide/migrating-5.html)
        -   [Database integration](/en/guide/database-integration.html)
-   -   [API reference](/en/4x/api.html)
        -   [5.x (alpha)](/en/5x/api.html)
        -   [4.x](/en/4x/api.html)
        -   [3.x (deprecated)](/en/3x/api.html)
        -   [2.x (deprecated)](/2x/)
-   -   [Advanced topics](/en/advanced/developing-template-engines.html)
        -   [Template
            engines](/en/advanced/developing-template-engines.html)
        -   [Process managers](/en/advanced/pm.html)
        -   [Security updates](/en/advanced/security-updates.html)
        -   [Security best
            practices](/en/advanced/best-practice-security.html)
        -   [Performance best
            practices](/en/advanced/best-practice-performance.html)
        -   [Health checks and graceful
            shutdown](/en/advanced/healthcheck-graceful-shutdown.html)
-   -   [Resources](/en/resources/glossary.html)
        -   [Community](/en/resources/community.html)
        -   [Glossary](/en/resources/glossary.html)
        -   [Template Engines](/en/resources/template-engines.html)
        -   [Middleware](/en/resources/middleware.html)
        -   [Utility modules](/en/resources/utils.html)
        -   [Frameworks](/en/resources/frameworks.html)
        -   [Companies using
            Express](/en/resources/companies-using-express.html)
        -   [Open-source
            projects](/en/resources/open-source-using-express.html)
        -   [Books and blogs](/en/resources/books-blogs.html)
        -   [Contributing to Express](/en/resources/contributing.html)
        -   [Release Change Log](/en/changelog/4x.html)

</div>

<div id="overlay">

</div>

<div id="page-doc" markdown="1">

Writing middleware for use in Express apps
==========================================

Overview
--------

*Middleware* functions are functions that have access to the [request
object](/en/4x/api.html#req) (`req`), the [response
object](/en/4x/api.html#res) (`res`), and the `next` function in the
application’s request-response cycle. The `next` function is a function
in the Express router which, when invoked, executes the middleware
succeeding the current middleware.

Middleware functions can perform the following tasks:

-   Execute any code.
-   Make changes to the request and the response objects.
-   End the request-response cycle.
-   Call the next middleware in the stack.

If the current middleware function does not end the request-response
cycle, it must call `next()` to pass control to the next middleware
function. Otherwise, the request will be left hanging.

The following figure shows the elements of a middleware function call:

+--------------------------------------+--------------------------------------+
| ![](/images/express-mw.png){#mw-fig- | <div id="callout1" class="callout">  |
| img}                                 |                                      |
|                                      | HTTP method for which the middleware |
|                                      | function applies.                    |
|                                      |                                      |
|                                      | </div>                               |
|                                      |                                      |
|                                      | <div id="callout2" class="callout">  |
|                                      |                                      |
|                                      | Path (route) for which the           |
|                                      | middleware function applies.         |
|                                      |                                      |
|                                      | </div>                               |
|                                      |                                      |
|                                      | <div id="callout3" class="callout">  |
|                                      |                                      |
|                                      | The middleware function.             |
|                                      |                                      |
|                                      | </div>                               |
|                                      |                                      |
|                                      | <div id="callout4" class="callout">  |
|                                      |                                      |
|                                      | Callback argument to the middleware  |
|                                      | function, called "next" by           |
|                                      | convention.                          |
|                                      |                                      |
|                                      | </div>                               |
|                                      |                                      |
|                                      | <div id="callout5" class="callout">  |
|                                      |                                      |
|                                      | HTTP [response](/en/4x/api.html#res) |
|                                      | argument to the middleware function, |
|                                      | called "res" by convention.          |
|                                      |                                      |
|                                      | </div>                               |
|                                      |                                      |
|                                      | <div id="callout6" class="callout">  |
|                                      |                                      |
|                                      | HTTP [request](/en/4x/api.html#req)  |
|                                      | argument to the middleware function, |
|                                      | called "req" by convention.          |
|                                      |                                      |
|                                      | </div>                               |
+--------------------------------------+--------------------------------------+

Example
-------

Here is an example of a simple “Hello World” Express application. The
remainder of this article will define and add two middleware functions
to the application: one called `myLogger` that prints a simple log
message and another called `requestTime` that displays the timestamp of
the HTTP request.

    var express = require('express')
    var app = express()

    app.get('/', function (req, res) {
      res.send('Hello World!')
    })

    app.listen(3000)

### Middleware function myLogger

Here is a simple example of a middleware function called “myLogger”.
This function just prints “LOGGED” when a request to the app passes
through it. The middleware function is assigned to a variable named
`myLogger`.

    var myLogger = function (req, res, next) {
      console.log('LOGGED')
      next()
    }

<div class="doc-box doc-notice">

Notice the call above to `next()`. Calling this function invokes the
next middleware function in the app. The `next()` function is not a part
of the Node.js or Express API, but is the third argument that is passed
to the middleware function. The `next()` function could be named
anything, but by convention it is always named “next”. To avoid
confusion, always use this convention.

</div>

To load the middleware function, call `app.use()`, specifying the
middleware function. For example, the following code loads the
`myLogger` middleware function before the route to the root path (/).

    var express = require('express')
    var app = express()

    var myLogger = function (req, res, next) {
      console.log('LOGGED')
      next()
    }

    app.use(myLogger)

    app.get('/', function (req, res) {
      res.send('Hello World!')
    })

    app.listen(3000)

Every time the app receives a request, it prints the message “LOGGED” to
the terminal.

The order of middleware loading is important: middleware functions that
are loaded first are also executed first.

If `myLogger` is loaded after the route to the root path, the request
never reaches it and the app doesn’t print “LOGGED”, because the route
handler of the root path terminates the request-response cycle.

The middleware function `myLogger` simply prints a message, then passes
on the request to the next middleware function in the stack by calling
the `next()` function.

### Middleware function requestTime

Next, we’ll create a middleware function called “requestTime” and add a
property called `requestTime` to the request object.

    var requestTime = function (req, res, next) {
      req.requestTime = Date.now()
      next()
    }

The app now uses the `requestTime` middleware function. Also, the
callback function of the root path route uses the property that the
middleware function adds to `req` (the request object).

    var express = require('express')
    var app = express()

    var requestTime = function (req, res, next) {
      req.requestTime = Date.now()
      next()
    }

    app.use(requestTime)

    app.get('/', function (req, res) {
      var responseText = 'Hello World!<br>'
      responseText += '<small>Requested at: ' + req.requestTime + '</small>'
      res.send(responseText)
    })

    app.listen(3000)

When you make a request to the root of the app, the app now displays the
timestamp of your request in the browser.

Because you have access to the request object, the response object, the
next middleware function in the stack, and the whole Node.js API, the
possibilities with middleware functions are endless.

For more information about Express middleware, see: [Using Express
middleware](/en/guide/using-middleware.html).

Configurable middleware
-----------------------

If you need your middleware to be configurable, export a function which
accepts an options object or other parameters, which, then returns the
middleware implementation based on the input parameters.

File: `my-middleware.js`

    module.exports = function (options) {
      return function (req, res, next) {
        // Implement the middleware function based on the options object
        next()
      }
    }

The middleware can now be used as shown below.

    var mw = require('./my-middleware.js')

    app.use(mw({ option1: '1', option2: '2' }))

Refer to [cookie-session](https://github.com/expressjs/cookie-session)
and [compression](https://github.com/expressjs/compression) for examples
of configurable middleware.

</div>

</div>

[![](/images/arrow.png)](#){#top}
<div id="doc-langs" class="section">

Documentation translations provided by
[StrongLoop/IBM](http://strongloop.com): [French](/fr/), [German](/de/),
[Spanish](/es/), [Italian](/it/), [Japanese](/ja/), [Russian](/ru/),
[Chinese](/zh-cn/), [Traditional Chinese](/zh-tw/), [Korean](/ko/),
[Portuguese](/pt-br/).\
Community translation available for: [Slovak](/sk/), [Ukrainian](/uk/),
[Uzbek](/uz/), [Turkish](/tr/) and [Thai](/th/).

</div>

<div id="footer-content">

<div id="github">

[Star](https://github.com/expressjs/expressjs.com){.github-button}

</div>

<div id="sponsor">

[Express](https://github.com/expressjs/express/) is a project of the
[](http://nodejs.org/foundation)Node.js Foundation.

</div>

<div id="fork">

[Fork the website on
GitHub](https://github.com/expressjs/expressjs.com).

</div>

<div>

Copyright © 2017 StrongLoop, IBM, and other expressjs.com contributors.

</div>

</div>

<div id="license">

[![Creative Commons
License](https://i.creativecommons.org/l/by-sa/3.0/us/80x15.png)](http://creativecommons.org/licenses/by-sa/3.0/us/)
This work is licensed under a [Creative Commons Attribution-ShareAlike
3.0 United States
License](http://creativecommons.org/licenses/by-sa/3.0/us/).

</div>
