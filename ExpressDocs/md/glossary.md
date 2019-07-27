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
-   -   [Guide](/en/guide/routing.html)
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
-   -   [Resources](/en/resources/glossary.html){.active}
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

Glossary
========

### application

In general, one or more programs that are designed to carry out
operations for a specific purpose. In the context of Express, a program
that uses the Express API running on the Node.js platform. Might also
refer to an [app object](/en/api.html#express).

### API

Application programming interface. Spell out the abbreviation when it is
first used.

### Express

A fast, un-opinionated, minimalist web framework for Node.js
applications. In general, “Express” is preferred to “Express.js,” though
the latter is acceptable.

### libuv

A multi-platform support library which focuses on asynchronous I/O,
primarily developed for use by Node.js.

### middleware

A function that is invoked by the Express routing layer before the final
request handler, and thus sits in the middle between a raw request and
the final intended route. A few fine points of terminology around
middleware:

-   `var foo = require('middleware')` is called *requiring* or *using* a
    Node.js module. Then the statement `var mw = foo()` typically
    returns the middleware.
-   `app.use(mw)` is called *adding the middleware to the global
    processing stack*.
-   `app.get('/foo', mw, function (req, res) { ... })` is called *adding
    the middleware to the “GET /foo” processing stack*.

### Node.js {#nodejs}

A software platform that is used to build scalable network applications.
Node.js uses JavaScript as its scripting language, and achieves high
throughput via non-blocking I/O and a single-threaded event loop. See
[nodejs.org](https://nodejs.org/en/). **Usage note**: Initially,
“Node.js,” thereafter “Node”.

### open-source, open source

When used as an adjective, hyphenate; for example: “This is open-source
software.” See [Open-source software on
Wikipedia](http://en.wikipedia.org/wiki/Open-source_software). Note:
Although it is common not to hyphenate this term, we are using the
standard English rules for hyphenating a compound adjective.

### request

An HTTP request. A client submits an HTTP request message to a server,
which returns a response. The request must use one of several [request
methods](https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol#Request_methods)
such as GET, POST, and so on.

### response

An HTTP response. A server returns an HTTP response message to the
client. The response contains completion status information about the
request and might also contain requested content in its message body.

### route

Part of a URL that identifies a resource. For example, in
`http://foo.com/products/id`, “/products/id” is the route.

### router

See [router](/en/api.html#router) in the API reference.

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
