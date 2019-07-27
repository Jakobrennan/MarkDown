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

Error Handling
==============

*Error Handling* refers to how Express catches and processes errors that
occur both synchronously and asynchronously. Express comes with a
default error handler so you don’t need to write your own to get
started.

Catching Errors
---------------

It’s important to ensure that Express catches all errors that occur
while running route handlers and middleware.

Errors that occur in synchronous code inside route handlers and
middleware require no extra work. If synchronous code throws an error,
then Express will catch and process it. For example:

    app.get('/', function (req, res) {
      throw new Error('BROKEN') // Express will catch this on its own.
    })

For errors returned from asynchronous functions invoked by route
handlers and middleware, you must pass them to the `next()` function,
where Express will catch and process them. For example:

    app.get('/', function (req, res, next) {
      fs.readFile('/file-does-not-exist', function (err, data) {
        if (err) {
          next(err) // Pass errors to Express.
        } else {
          res.send(data)
        }
      })
    })

If you pass anything to the `next()` function (except the string
`'route'`), Express regards the current request as being an error and
will skip any remaining non-error handling routing and middleware
functions.

If the callback in a sequence provides no data, only errors, you can
simplify this code as follows:

    app.get('/', [
      function (req, res, next) {
        fs.writeFile('/inaccessible-path', 'data', next)
      },
      function (req, res) {
        res.send('OK')
      }
    ])

In the above example `next` is provided as the callback for
`fs.writeFile`, which is called with or without errors. If there is no
error the second handler is executed, otherwise Express catches and
processes the error.

You must catch errors that occur in asynchronous code invoked by route
handlers or middleware and pass them to Express for processing. For
example:

    app.get('/', function (req, res, next) {
      setTimeout(function () {
        try {
          throw new Error('BROKEN')
        } catch (err) {
          next(err)
        }
      }, 100)
    })

The above example uses a `try...catch` block to catch errors in the
asynchronous code and pass them to Express. If the `try...catch` block
were omitted, Express would not catch the error since it is not part of
the synchronous handler code.

Use promises to avoid the overhead of the `try..catch` block or when
using functions that return promises. For example:

    app.get('/', function (req, res, next) {
      Promise.resolve().then(function () {
        throw new Error('BROKEN')
      }).catch(next) // Errors will be passed to Express.
    })

Since promises automatically catch both synchronous errors and rejected
promises, you can simply provide `next` as the final catch handler and
Express will catch errors, because the catch handler is given the error
as the first argument.

You could also use a chain of handlers to rely on synchronous error
catching, by reducing the asynchronous code to something trivial. For
example:

    app.get('/', [
      function (req, res, next) {
        fs.readFile('/maybe-valid-file', 'utf-8', function (err, data) {
          res.locals.data = data
          next(err)
        })
      },
      function (req, res) {
        res.locals.data = res.locals.data.split(',')[1]
        res.send(res.locals.data)
      }
    ])

The above example has a couple of trivial statements from the `readFile`
call. If `readFile` causes an error, then it passes the error to
Express, otherwise you quickly return to the world of synchronous error
handling in the next handler in the chain. Then, the example above tries
to process the data. If this fails then the synchronous error handler
will catch it. If you had done this processing inside the `readFile`
callback then the application might exit and the Express error handlers
would not run.

Whichever method you use, if you want Express error handlers to be
called in and the application to survive, you must ensure that Express
receives the error.

The default error handler
-------------------------

Express comes with a built-in error handler that takes care of any
errors that might be encountered in the app. This default error-handling
middleware function is added at the end of the middleware function
stack.

If you pass an error to `next()` and you do not handle it in a custom
error handler, it will be handled by the built-in error handler; the
error will be written to the client with the stack trace. The stack
trace is not included in the production environment.

<div class="doc-box doc-info">

Set the environment variable `NODE_ENV` to `production`, to run the app
in production mode.

</div>

If you call `next()` with an error after you have started writing the
response (for example, if you encounter an error while streaming the
response to the client) the Express default error handler closes the
connection and fails the request.

So when you add a custom error handler, you must delegate to the default
Express error handler, when the headers have already been sent to the
client:

    function errorHandler (err, req, res, next) {
      if (res.headersSent) {
        return next(err)
      }
      res.status(500)
      res.render('error', { error: err })
    }

Note that the default error handler can get triggered if you call
`next()` with an error in your code more than once, even if custom error
handling middleware is in place.

Writing error handlers
----------------------

Define error-handling middleware functions in the same way as other
middleware functions, except error-handling functions have four
arguments instead of three: `(err, req, res, next)`. For example:

    app.use(function (err, req, res, next) {
      console.error(err.stack)
      res.status(500).send('Something broke!')
    })

You define error-handling middleware last, after other `app.use()` and
routes calls; for example:

    var bodyParser = require('body-parser')
    var methodOverride = require('method-override')

    app.use(bodyParser.urlencoded({
      extended: true
    }))
    app.use(bodyParser.json())
    app.use(methodOverride())
    app.use(function (err, req, res, next) {
      // logic
    })

Responses from within a middleware function can be in any format, such
as an HTML error page, a simple message, or a JSON string.

For organizational (and higher-level framework) purposes, you can define
several error-handling middleware functions, much as you would with
regular middleware functions. For example, to define an error-handler
for requests made by using `XHR` and those without:

    var bodyParser = require('body-parser')
    var methodOverride = require('method-override')

    app.use(bodyParser.urlencoded({
      extended: true
    }))
    app.use(bodyParser.json())
    app.use(methodOverride())
    app.use(logErrors)
    app.use(clientErrorHandler)
    app.use(errorHandler)

In this example, the generic `logErrors` might write request and error
information to `stderr`, for example:

    function logErrors (err, req, res, next) {
      console.error(err.stack)
      next(err)
    }

Also in this example, `clientErrorHandler` is defined as follows; in
this case, the error is explicitly passed along to the next one.

Notice that when *not* calling “next” in an error-handling function, you
are responsible for writing (and ending) the response. Otherwise those
requests will “hang” and will not be eligible for garbage collection.

    function clientErrorHandler (err, req, res, next) {
      if (req.xhr) {
        res.status(500).send({ error: 'Something failed!' })
      } else {
        next(err)
      }
    }

Implement the “catch-all” `errorHandler` function as follows (for
example):

    function errorHandler (err, req, res, next) {
      res.status(500)
      res.render('error', { error: err })
    }

If you have a route handler with multiple callback functions you can use
the `route` parameter to skip to the next route handler. For example:

    app.get('/a_route_behind_paywall',
      function checkIfPaidSubscriber (req, res, next) {
        if (!req.user.hasPaid) {
          // continue handling this request
          next('route')
        } else {
          next()
        }
      }, function getPaidContent (req, res, next) {
        PaidContent.find(function (err, doc) {
          if (err) return next(err)
          res.json(doc)
        })
      })

In this example, the `getPaidContent` handler will be skipped but any
remaining handlers in `app` for `/a_route_behind_paywall` would continue
to be executed.

<div class="doc-box doc-info">

Calls to `next()` and `next(err)` indicate that the current handler is
complete and in what state. `next(err)` will skip all remaining handlers
in the chain except for those that are set up to handle errors as
described above.

</div>

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
