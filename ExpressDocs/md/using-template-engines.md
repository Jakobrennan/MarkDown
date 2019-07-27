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

Using template engines with Express
===================================

A *template engine* enables you to use static template files in your
application. At runtime, the template engine replaces variables in a
template file with actual values, and transforms the template into an
HTML file sent to the client. This approach makes it easier to design an
HTML page.

Some popular template engines that work with Express are
[Pug](https://pugjs.org/api/getting-started.html),
[Mustache](https://www.npmjs.com/package/mustache), and
[EJS](https://www.npmjs.com/package/ejs). The [Express application
generator](/en/starter/generator.html) uses
[Jade](https://www.npmjs.com/package/jade) as its default, but it also
supports several others.

See [Template Engines (Express
wiki)](https://github.com/strongloop/express/wiki#template-engines) for
a list of template engines you can use with Express. See also [Comparing
JavaScript Templating Engines: Jade, Mustache, Dust and
More](https://strongloop.com/strongblog/compare-javascript-templates-jade-mustache-dust/).

<div class="doc-box doc-notice">

**Note**: Jade has been renamed to
[Pug](https://www.npmjs.com/package/pug). You can continue to use Jade
in your app, and it will work just fine. However if you want the latest
updates to the template engine, you must replace Jade with Pug in your
app.

</div>

To render template files, set the following [application setting
properties](/en/4x/api.html#app.set), set in `app.js` in the default app
created by the generator:

-   `views`, the directory where the template files are located. Eg:
    `app.set('views', './views')`. This defaults to the `views`
    directory in the application root directory.
-   `view engine`, the template engine to use. For example, to use the
    Pug template engine: `app.set('view engine', 'pug')`.

Then install the corresponding template engine npm package; for example
to install Pug:

    $ npm install pug --save

<div class="doc-box doc-notice">

Express-compliant template engines such as Jade and Pug export a
function named `__express(filePath, options, callback)`, which is called
by the `res.render()` function to render the template code.

Some template engines do not follow this convention. The
[Consolidate.js](https://www.npmjs.org/package/consolidate) library
follows this convention by mapping all of the popular Node.js template
engines, and therefore works seamlessly within Express.

</div>

After the view engine is set, you don’t have to specify the engine or
load the template engine module in your app; Express loads the module
internally, as shown below (for the above example).

    app.set('view engine', 'pug')

Create a Pug template file named `index.pug` in the `views` directory,
with the following content:

    html
      head
        title= title
      body
        h1= message

Then create a route to render the `index.pug` file. If the `view engine`
property is not set, you must specify the extension of the `view` file.
Otherwise, you can omit it.

    app.get('/', function (req, res) {
      res.render('index', { title: 'Hey', message: 'Hello there!' })
    })

When you make a request to the home page, the `index.pug` file will be
rendered as HTML.

Note: The view engine cache does not cache the contents of the
template’s output, only the underlying template itself. The view is
still re-rendered with every request even when the cache is on.

To learn more about how template engines work in Express, see:
[“Developing template engines for
Express”](/en/advanced/developing-template-engines.html).

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
