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

Moving to Express 5
===================

Overview
--------

Express 5.0 is still in the alpha release stage, but here is a preview
of the changes that will be in the release and how to migrate your
Express 4 app to Express 5.

Express 5 is not very different from Express 4: The changes to the API
are not as significant as from 3.0 to 4.0. Although the basic API
remains the same, there are still breaking changes; in other words an
existing Express 4 program might not work if you update it to use
Express 5.

To install the latest alpha and to preview Express 5, enter the
following command in your application root directory:

    $ npm install express@>=5.0.0-alpha.1 --save

You can then run your automated tests to see what fails, and fix
problems according to the updates listed below. After addressing test
failures, run your app to see what errors occur. You’ll find out right
away if the app uses any methods or properties that are not supported.

Changes in Express 5 {#changes}
--------------------

Here is the list of changes (as of the alpha 2 release ) that will
affect you as a user of Express. See the [pull
request](https://github.com/strongloop/express/pull/2237) for a list of
all the planned features.

**Removed methods and properties**

-   [app.del()](#app.del)
-   [app.param(fn)](#app.param)
-   [Pluralized method names](#plural)
-   [Leading colon in name argument to app.param(name, fn)](#leading)
-   [req.param(name)](#req.param)
-   [res.json(obj, status)](#res.json)
-   [res.jsonp(obj, status)](#res.jsonp)
-   [res.send(body, status)](#res.send.body)
-   [res.send(status)](#res.send.status)
-   [res.sendfile()](#res.sendfile)

**Changed**

-   [app.router](#app.router)
-   [req.host](#req.host)
-   [req.query](#req.query)

**Improvements**

-   [res.render()](#res.render)

### Removed methods and properties

If you use any of these methods or properties in your app, it will
crash. So, you’ll need to change your app after you update to version 5.

#### app.del()

Express 5 no longer supports the `app.del()` function. If you use this
function an error is thrown. For registering HTTP DELETE routes, use the
`app.delete()` function instead.

Initially `del` was used instead of `delete`, because `delete` is a
reserved keyword in JavaScript. However, as of ECMAScript 6, `delete`
and other reserved keywords can legally be used as property names.

#### app.param(fn) {#app.param}

The `app.param(fn)` signature was used for modifying the behavior of the
`app.param(name, fn)` function. It has been deprecated since v4.11.0,
and Express 5 no longer supports it at all.

#### Pluralized method names {#plural}

The following method names have been pluralized. In Express 4, using the
old methods resulted in a deprecation warning. Express 5 no longer
supports them at all:

`req.acceptsCharset()` is replaced by `req.acceptsCharsets()`.

`req.acceptsEncoding()` is replaced by `req.acceptsEncodings()`.

`req.acceptsLanguage()` is replaced by `req.acceptsLanguages()`.

#### Leading colon (:) in the name for app.param(name, fn) {#leading}

A leading colon character (:) in the name for the `app.param(name, fn)`
function is a remnant of Express 3, and for the sake of backwards
compatibility, Express 4 supported it with a deprecation notice. Express
5 will silently ignore it and use the name parameter without prefixing
it with a colon.

This should not affect your code if you follow the Express 4
documentation of [app.param](/en/4x/api.html#app.param), as it makes no
mention of the leading colon.

#### req.param(name) {#req.param}

This potentially confusing and dangerous method of retrieving form data
has been removed. You will now need to specifically look for the
submitted parameter name in the `req.params`, `req.body`, or `req.query`
object.

#### res.json(obj, status) {#res.json}

Express 5 no longer supports the signature `res.json(obj, status)`.
Instead, set the status and then chain it to the `res.json()` method
like this: `res.status(status).json(obj)`.

#### res.jsonp(obj, status) {#res.jsonp}

Express 5 no longer supports the signature `res.jsonp(obj, status)`.
Instead, set the status and then chain it to the `res.jsonp()` method
like this: `res.status(status).jsonp(obj)`.

#### res.send(body, status) {#res.send.body}

Express 5 no longer supports the signature `res.send(obj, status)`.
Instead, set the status and then chain it to the `res.send()` method
like this: `res.status(status).send(obj)`.

#### res.send(status) {#res.send.status}

Express 5 no longer supports the signature `res.send(status)`, where
*`status`* is a number. Instead, use the `res.sendStatus(statusCode)`
function, which sets the HTTP response header status code and sends the
text version of the code: “Not Found”, “Internal Server Error”, and so
on. If you need to send a number by using the `res.send()` function,
quote the number to convert it to a string, so that Express does not
interpret it as an attempt to use the unsupported old signature.

#### res.sendfile()

The `res.sendfile()` function has been replaced by a camel-cased version
`res.sendFile()` in Express 5.

### Changed

#### app.router

The `app.router` object, which was removed in Express 4, has made a
comeback in Express 5. In the new version, this object is a just a
reference to the base Express router, unlike in Express 3, where an app
had to explicitly load it.

#### req.host

In Express 4, the `req.host` function incorrectly stripped off the port
number if it was present. In Express 5 the port number is maintained.

#### req.query

In Express 4.7 and Express 5 onwards, the query parser option can accept
`false` to disable query string parsing when you want to use your own
function for query string parsing logic.

### Improvements

#### res.render()

This method now enforces asynchronous behavior for all view engines,
avoiding bugs caused by view engines that had a synchronous
implementation and that violated the recommended interface.

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
