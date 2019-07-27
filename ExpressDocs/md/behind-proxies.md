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

Express behind proxies
======================

When running an Express app behind a proxy, set (by using
[app.set()](/en/4x/api.html#app.set)) the application variable
`trust proxy` to one of the values listed in the following table.

<div class="doc-box doc-info">

Although the app will not fail to run if the application variable
`trust proxy` is not set, it will incorrectly register the proxy’s IP
address as the client IP address unless `trust proxy` is configured.

</div>

+--------------------------------------+--------------------------------------+
| Type                                 | Value                                |
+======================================+======================================+
| Boolean                              | If `true`, the client’s IP address   |
|                                      | is understood as the left-most entry |
|                                      | in the `X-Forwarded-*` header.       |
|                                      |                                      |
|                                      | If `false`, the app is understood as |
|                                      | directly facing the Internet and the |
|                                      | client’s IP address is derived from  |
|                                      | `req.connection.remoteAddress`. This |
|                                      | is the default setting.              |
+--------------------------------------+--------------------------------------+
| IP addresses                         | An IP address, subnet, or an array   |
|                                      | of IP addresses and subnets to       |
|                                      | trust. The following list shows the  |
|                                      | pre-configured subnet names:         |
|                                      |                                      |
|                                      | -   loopback - `127.0.0.1/8`,        |
|                                      |     `::1/128`                        |
|                                      | -   linklocal - `169.254.0.0/16`,    |
|                                      |     `fe80::/10`                      |
|                                      | -   uniquelocal - `10.0.0.0/8`,      |
|                                      |     `172.16.0.0/12`,                 |
|                                      |     `192.168.0.0/16`, `fc00::/7`     |
|                                      |                                      |
|                                      | You can set IP addresses in any of   |
|                                      | the following ways:                  |
|                                      |                                      |
|                                      |     app.set('trust proxy', 'loopback |
|                                      | ') // specify a single subnet        |
|                                      |     app.set('trust proxy', 'loopback |
|                                      | , 123.123.123.123') // specify a sub |
|                                      | net and an address                   |
|                                      |     app.set('trust proxy', 'loopback |
|                                      | , linklocal, uniquelocal') // specif |
|                                      | y multiple subnets as CSV            |
|                                      |     app.set('trust proxy', ['loopbac |
|                                      | k', 'linklocal', 'uniquelocal']) //  |
|                                      | specify multiple subnets as an array |
|                                      |                                      |
|                                      | When specified, the IP addresses or  |
|                                      | the subnets are excluded from the    |
|                                      | address determination process, and   |
|                                      | the untrusted IP address nearest to  |
|                                      | the application server is determined |
|                                      | as the client’s IP address.          |
+--------------------------------------+--------------------------------------+
| Number                               | Trust the `n`th hop from the         |
|                                      | front-facing proxy server as the     |
|                                      | client.                              |
+--------------------------------------+--------------------------------------+
| Function                             | Custom trust implementation. Use     |
|                                      | this only if you know what you are   |
|                                      | doing.                               |
|                                      |                                      |
|                                      |     app.set('trust proxy', function  |
|                                      | (ip) {                               |
|                                      |       if (ip === '127.0.0.1' || ip = |
|                                      | == '123.123.123.123') return true // |
|                                      |  trusted IPs                         |
|                                      |       else return false              |
|                                      |     })                               |
+--------------------------------------+--------------------------------------+

Enabling `trust proxy` will have the following impact:

-   The value of [req.hostname](/en/api.html#req.hostname) is derived
    from the value set in the `X-Forwarded-Host` header, which can be
    set by the client or by the proxy.

-   `X-Forwarded-Proto` can be set by the reverse proxy to tell the app
    whether it is `https` or `http` or even an invalid name. This value
    is reflected by [req.protocol](/en/api.html#req.protocol).

-   The [req.ip](/en/api.html#req.ip) and
    [req.ips](/en/api.html#req.ips) values are populated with the list
    of addresses from `X-Forwarded-For`.

The `trust proxy` setting is implemented using the
[proxy-addr](https://www.npmjs.com/package/proxy-addr) package. For more
information, see its documentation.

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
