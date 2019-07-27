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

Moving to Express 4
===================

Overview
--------

Express 4 is a breaking change from Express 3. That means an existing
Express 3 app will *not* work if you update the Express version in its
dependencies.

This article covers:

-   [Changes in Express 4](#changes).
-   [An example](#example-migration) of migrating an Express 3 app to
    Express 4.
-   [Upgrading to the Express 4 app generator](#app-gen).

Changes in Express 4 {#changes}
--------------------

There are several significant changes in Express 4:

-   [Changes to Express core and middleware system.](#core-changes) The
    dependencies on Connect and built-in middleware were removed, so you
    must add middleware yourself.
-   [Changes to the routing system.](#routing)
-   [Various other changes.](#other-changes)

See also:

-   [New features
    in 4.x.](https://github.com/strongloop/express/wiki/New-features-in-4.x)
-   [Migrating from 3.x
    to 4.x.](https://github.com/strongloop/express/wiki/Migrating-from-3.x-to-4.x)

### Changes to Express core and middleware system {#core-changes}

Express 4 no longer depends on Connect, and removes all built-in
middleware from its core, except for the `express.static` function. This
means that Express is now an independent routing and middleware web
framework, and Express versioning and releases are not affected by
middleware updates.

Without built-in middleware, you must explicitly add all the middleware
that is required to run your app. Simply follow these steps:

1.  Install the module: `npm install --save <module-name>`
2.  In your app, require the module: `require('module-name')`
3.  Use the module according to its documentation: `app.use( ... )`

The following table lists Express 3 middleware and their counterparts in
Express 4.

  Express 3                  Express 4
  -------------------------- ---------------------------------------------------------------------------------------------------------
  `express.bodyParser`       [body-parser](https://github.com/expressjs/body-parser) + [multer](https://github.com/expressjs/multer)
  `express.compress`         [compression](https://github.com/expressjs/compression)
  `express.cookieSession`    [cookie-session](https://github.com/expressjs/cookie-session)
  `express.cookieParser`     [cookie-parser](https://github.com/expressjs/cookie-parser)
  `express.logger`           [morgan](https://github.com/expressjs/morgan)
  `express.session`          [express-session](https://github.com/expressjs/session)
  `express.favicon`          [serve-favicon](https://github.com/expressjs/serve-favicon)
  `express.responseTime`     [response-time](https://github.com/expressjs/response-time)
  `express.errorHandler`     [errorhandler](https://github.com/expressjs/errorhandler)
  `express.methodOverride`   [method-override](https://github.com/expressjs/method-override)
  `express.timeout`          [connect-timeout](https://github.com/expressjs/timeout)
  `express.vhost`            [vhost](https://github.com/expressjs/vhost)
  `express.csrf`             [csurf](https://github.com/expressjs/csurf)
  `express.directory`        [serve-index](https://github.com/expressjs/serve-index)
  `express.static`           [serve-static](https://github.com/expressjs/serve-static)

Here is the [complete
list](https://github.com/senchalabs/connect#middleware) of Express 4
middleware.

In most cases, you can simply replace the old version 3 middleware with
its Express 4 counterpart. For details, see the module documentation in
GitHub.

#### `app.use` accepts parameters {#app-use}

In version 4 you can use a variable parameter to define the path where
middleware functions are loaded, then read the value of the parameter
from the route handler. For example:

    app.use('/book/:id', function (req, res, next) {
      console.log('ID:', req.params.id)
      next()
    })

### The routing system {#routing}

Apps now implicitly load routing middleware, so you no longer have to
worry about the order in which middleware is loaded with respect to the
`router` middleware.

The way you define routes is unchanged, but the routing system has two
new features to help organize your routes:

-   A new method, `app.route()`, to create chainable route handlers for
    a route path.
-   A new class, `express.Router`, to create modular mountable
    route handlers.

#### `app.route()` method {#app-route}

The new `app.route()` method enables you to create chainable route
handlers for a route path. Because the path is specified in a single
location, creating modular routes is helpful, as is reducing redundancy
and typos. For more information about routes, see [`Router()`
documentation](/en/4x/api.html#router).

Here is an example of chained route handlers that are defined by using
the `app.route()` function.

    app.route('/book')
      .get(function (req, res) {
        res.send('Get a random book')
      })
      .post(function (req, res) {
        res.send('Add a book')
      })
      .put(function (req, res) {
        res.send('Update the book')
      })

#### `express.Router` class {#express-router}

The other feature that helps to organize routes is a new class,
`express.Router`, that you can use to create modular mountable route
handlers. A `Router` instance is a complete middleware and routing
system; for this reason it is often referred to as a “mini-app”.

The following example creates a router as a module, loads middleware in
it, defines some routes, and mounts it on a path on the main app.

For example, create a router file named `birds.js` in the app directory,
with the following content:

    var express = require('express')
    var router = express.Router()

    // middleware specific to this router
    router.use(function timeLog (req, res, next) {
      console.log('Time: ', Date.now())
      next()
    })
    // define the home page route
    router.get('/', function (req, res) {
      res.send('Birds home page')
    })
    // define the about route
    router.get('/about', function (req, res) {
      res.send('About birds')
    })

    module.exports = router

Then, load the router module in the app:

    var birds = require('./birds')

    // ...

    app.use('/birds', birds)

The app will now be able to handle requests to the `/birds` and
`/birds/about` paths, and will call the `timeLog` middleware that is
specific to the route.

### Other changes

The following table lists other small but important changes in Express
4:

+--------------------------------------+--------------------------------------+
| Object                               | Description                          |
+======================================+======================================+
| Node.js                              | Express 4 requires Node.js 0.10.x or |
|                                      | later and has dropped support for    |
|                                      | Node.js 0.8.x.                       |
+--------------------------------------+--------------------------------------+
| `http.createServer()`                | The `http` module is no longer       |
|                                      | needed, unless you need to directly  |
|                                      | work with it (socket.io/SPDY/HTTPS). |
|                                      | The app can be started by using the  |
|                                      | `app.listen()` function.             |
+--------------------------------------+--------------------------------------+
| `app.configure()`                    | The `app.configure()` function has   |
|                                      | been removed. Use the                |
|                                      | `process.env.NODE_ENV` or            |
|                                      | `app.get('env')` function to detect  |
|                                      | the environment and configure the    |
|                                      | app accordingly.                     |
+--------------------------------------+--------------------------------------+
| `json spaces`                        | The `json spaces` application        |
|                                      | property is disabled by default in   |
|                                      | Express 4.                           |
+--------------------------------------+--------------------------------------+
| `req.accepted()`                     | Use `req.accepts()`,                 |
|                                      | `req.acceptsEncodings()`,            |
|                                      | `req.acceptsCharsets()`, and         |
|                                      | `req.acceptsLanguages()`.            |
+--------------------------------------+--------------------------------------+
| `res.location()`                     | No longer resolves relative URLs.    |
+--------------------------------------+--------------------------------------+
| `req.params`                         | Was an array; now an object.         |
+--------------------------------------+--------------------------------------+
| `res.locals`                         | Was a function; now an object.       |
+--------------------------------------+--------------------------------------+
| `res.headerSent`                     | Changed to `res.headersSent`.        |
+--------------------------------------+--------------------------------------+
| `app.route`                          | Now available as `app.mountpath`.    |
+--------------------------------------+--------------------------------------+
| `res.on('header')`                   | Removed.                             |
+--------------------------------------+--------------------------------------+
| `res.charset`                        | Removed.                             |
+--------------------------------------+--------------------------------------+
| `res.setHeader('Set-Cookie', val)`   | Functionality is now limited to      |
|                                      | setting the basic cookie value. Use  |
|                                      | `res.cookie()` for added             |
|                                      | functionality.                       |
+--------------------------------------+--------------------------------------+

Example app migration {#example-migration}
---------------------

Here is an example of migrating an Express 3 application to Express 4.
The files of interest are `app.js` and `package.json`.

### Version 3 app

#### `app.js`

Consider an Express v.3 application with the following `app.js` file:

    var express = require('express')
    var routes = require('./routes')
    var user = require('./routes/user')
    var http = require('http')
    var path = require('path')

    var app = express()

    // all environments
    app.set('port', process.env.PORT || 3000)
    app.set('views', path.join(__dirname, 'views'))
    app.set('view engine', 'pug')
    app.use(express.favicon())
    app.use(express.logger('dev'))
    app.use(express.methodOverride())
    app.use(express.session({ secret: 'your secret here' }))
    app.use(express.bodyParser())
    app.use(app.router)
    app.use(express.static(path.join(__dirname, 'public')))

    // development only
    if (app.get('env') === 'development') {
      app.use(express.errorHandler())
    }

    app.get('/', routes.index)
    app.get('/users', user.list)

    http.createServer(app).listen(app.get('port'), function () {
      console.log('Express server listening on port ' + app.get('port'))
    })

#### `package.json`

The accompanying version 3 `package.json` file might look something like
this:

    {
      "name": "application-name",
      "version": "0.0.1",
      "private": true,
      "scripts": {
        "start": "node app.js"
      },
      "dependencies": {
        "express": "3.12.0",
        "pug": "*"
      }
    }

### Process

Begin the migration process by installing the required middleware for
the Express 4 app and updating Express and Pug to their respective
latest version with the following command:

    $ npm install serve-favicon morgan method-override express-session body-parser multer errorhandler express@latest pug@latest --save

Make the following changes to `app.js`:

1.  The built-in Express middleware functions `express.favicon`,
    `express.logger`, `express.methodOverride`, `express.session`,
    `express.bodyParser` and `express.errorHandler` are no longer
    available on the `express` object. You must install their
    alternatives manually and load them in the app.

2.  You no longer need to load the `app.router` function. It is not a
    valid Express 4 app object, so remove the
    `app.use(app.router);` code.

3.  Make sure that the middleware functions are loaded in the correct
    order - load `errorHandler` after loading the app routes.

### Version 4 app

#### `package.json`

Running the above `npm` command will update `package.json` as follows:

    {
      "name": "application-name",
      "version": "0.0.1",
      "private": true,
      "scripts": {
        "start": "node app.js"
      },
      "dependencies": {
        "body-parser": "^1.5.2",
        "errorhandler": "^1.1.1",
        "express": "^4.8.0",
        "express-session": "^1.7.2",
        "pug": "^2.0.0",
        "method-override": "^2.1.2",
        "morgan": "^1.2.2",
        "multer": "^0.1.3",
        "serve-favicon": "^2.0.1"
      }
    }

#### `app.js`

Then, remove invalid code, load the required middleware, and make other
changes as necessary. The `app.js` file will look like this:

    var http = require('http')
    var express = require('express')
    var routes = require('./routes')
    var user = require('./routes/user')
    var path = require('path')

    var favicon = require('serve-favicon')
    var logger = require('morgan')
    var methodOverride = require('method-override')
    var session = require('express-session')
    var bodyParser = require('body-parser')
    var multer = require('multer')
    var errorHandler = require('errorhandler')

    var app = express()

    // all environments
    app.set('port', process.env.PORT || 3000)
    app.set('views', path.join(__dirname, 'views'))
    app.set('view engine', 'pug')
    app.use(favicon(path.join(__dirname, '/public/favicon.ico')))
    app.use(logger('dev'))
    app.use(methodOverride())
    app.use(session({
      resave: true,
      saveUninitialized: true,
      secret: 'uwotm8'
    }))
    app.use(bodyParser.json())
    app.use(bodyParser.urlencoded({ extended: true }))
    app.use(multer())
    app.use(express.static(path.join(__dirname, 'public')))

    app.get('/', routes.index)
    app.get('/users', user.list)

    // error handling middleware should be loaded after the loading the routes
    if (app.get('env') === 'development') {
      app.use(errorHandler())
    }

    var server = http.createServer(app)
    server.listen(app.get('port'), function () {
      console.log('Express server listening on port ' + app.get('port'))
    })

<div class="doc-box doc-info">

Unless you need to work directly with the `http` module
(socket.io/SPDY/HTTPS), loading it is not required, and the app can be
simply started this way:

    app.listen(app.get('port'), function () {
      console.log('Express server listening on port ' + app.get('port'))
    })

</div>

### Run the app

The migration process is complete, and the app is now an Express 4 app.
To confirm, start the app by using the following command:

    $ node .

Load <http://localhost:3000> and see the home page being rendered by
Express 4.

Upgrading to the Express 4 app generator {#app-gen}
----------------------------------------

The command-line tool to generate an Express app is still `express`, but
to upgrade to the new version, you must uninstall the Express 3 app
generator and then install the new `express-generator`.

### Installing

If you already have the Express 3 app generator installed on your
system, you must uninstall it:

    $ npm uninstall -g express

Depending on how your file and directory privileges are configured, you
might need to run this command with `sudo`.

Now install the new generator:

    $ npm install -g express-generator

Depending on how your file and directory privileges are configured, you
might need to run this command with `sudo`.

Now the `express` command on your system is updated to the Express 4
generator.

### Changes to the app generator

Command options and use largely remain the same, with the following
exceptions:

-   Removed the `--sessions` option.
-   Removed the `--jshtml` option.
-   Added the `--hogan` option to support
    [Hogan.js](http://twitter.github.io/hogan.js/).

### Example

Execute the following command to create an Express 4 app:

    $ express app4

If you look at the contents of the `app4/app.js` file, you will notice
that all the middleware functions (except `express.static`) that are
required for the app are loaded as independent modules, and the `router`
middleware is no longer explicitly loaded in the app.

You will also notice that the `app.js` file is now a Node.js module, in
contrast to the standalone app that was generated by the old generator.

After installing the dependencies, start the app by using the following
command:

    $ npm start

If you look at the npm start script in the `package.json` file, you will
notice that the actual command that starts the app is `node ./bin/www`,
which used to be `node app.js` in Express 3.

Because the `app.js` file that was generated by the Express 4 generator
is now a Node.js module, it can no longer be started independently as an
app (unless you modify the code). The module must be loaded in a Node.js
file and started via the Node.js file. The Node.js file is `./bin/www`
in this case.

Neither the `bin` directory nor the extensionless `www` file is
mandatory for creating an Express app or starting the app. They are just
suggestions made by the generator, so feel free to modify them to suit
your needs.

To get rid of the `www` directory and keep things the “Express 3 way”,
delete the line that says `module.exports = app;` at the end of the
`app.js` file, then paste the following code in its place:

    app.set('port', process.env.PORT || 3000)

    var server = app.listen(app.get('port'), function () {
      debug('Express server listening on port ' + server.address().port)
    })

Ensure that you load the `debug` module at the top of the `app.js` file
by using the following code:

    var debug = require('debug')('app4')

Next, change `"start": "node ./bin/www"` in the `package.json` file to
`"start": "node app.js"`.

You have now moved the functionality of `./bin/www` back to `app.js`.
This change is not recommended, but the exercise helps you to understand
how the `./bin/www` file works, and why the `app.js` file no longer
starts on its own.

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
