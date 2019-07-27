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
-   -   [Advanced
        topics](/en/advanced/developing-template-engines.html){.active}
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

Security updates
================

<div class="doc-box doc-notice">

Node.js vulnerabilities directly affect Express. Therefore [keep a watch
on Node.js vulnerabilities](http://blog.nodejs.org/vulnerability/) and
make sure you are using the latest stable version of Node.js.

</div>

The list below enumerates the Express vulnerabilities that were fixed in
the specified version update.

**NOTE**: If you believe you have discovered a security vulnerability in
Express, please see [Security Policies and
Procedures](/en/resources/contributing.html#security-policies-and-procedures).

4.x {#4x}
---

-   4.16.0
    -   The dependency `forwarded` has been updated to address a
        [vulnerability](https://nodesecurity.io/advisories/527). This
        may affect your application if the following APIs are used:
        `req.host`, `req.hostname`, `req.ip`, `req.ips`, `req.protocol`.
    -   The dependency `mime` has been updated to address a
        [vulnerability](https://nodesecurity.io/advisories/535), but
        this issue does not impact Express.
    -   The dependency `send` has been updated to provide a protection
        against a [Node.js 8.5.0
        vulnerability](https://nodejs.org/en/blog/vulnerability/september-2017-path-validation/).
        This only impacts running Express on the specific Node.js
        version 8.5.0.
-   4.15.5
    -   The dependency `debug` has been updated to address a
        [vulnerability](https://snyk.io/vuln/npm:debug:20170905), but
        this issue does not impact Express.
    -   The dependency `fresh` has been updated to address a
        [vulnerability](https://nodesecurity.io/advisories/526). This
        will affect your application if the following APIs are used:
        `express.static`, `req.fresh`, `res.json`, `res.jsonp`,
        `res.send`, `res.sendfile` `res.sendFile`, `res.sendStatus`.
-   4.15.3
    -   The dependency `ms` has been updated to address a
        [vulnerability](https://snyk.io/vuln/npm:ms:20170412). This may
        affect your application if untrusted string input is passed to
        the `maxAge` option in the following APIs: `express.static`,
        `res.sendfile`, and `res.sendFile`.
-   4.15.2
    -   The dependency `qs` has been updated to address a
        [vulnerability](https://snyk.io/vuln/npm:qs:20170213), but this
        issue does not impact Express. Updating to 4.15.2 is a good
        practice, but not required to address the vulnerability.
-   4.11.1
    -   Fixed root path disclosure vulnerability in `express.static`,
        `res.sendfile`, and `res.sendFile`
-   4.10.7
    -   Fixed open redirect vulnerability in `express.static`
        ([advisory](https://nodesecurity.io/advisories/serve-static-open-redirect),
        [CVE-2015-1164](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2015-1164)).
-   4.8.8
    -   Fixed directory traversal vulnerabilities in `express.static`
        ([advisory](http://nodesecurity.io/advisories/send-directory-traversal)
        ,
        [CVE-2014-6394](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2014-6394)).
-   4.8.4
    -   Node.js 0.10 can leak `fd`s in certain situations that affect
        `express.static` and `res.sendfile`. Malicious requests could
        cause `fd`s to leak and eventually lead to `EMFILE` errors and
        server unresponsiveness.
-   4.8.0
    -   Sparse arrays that have extremely high indexes in the query
        string could cause the process to run out of memory and crash
        the server.
    -   Extremely nested query string objects could cause the process to
        block and make the server unresponsive temporarily.

3.x {#3x}
---

<div class="doc-box doc-warn">

**Express 3.x IS NO LONGER MAINTAINED**

Known and unknown security issues in 3.x have not been addressed since
the last update (1 August, 2015). Using the 3.x line should not be
considered secure.

</div>

-   3.19.1
    -   Fixed root path disclosure vulnerability in `express.static`,
        `res.sendfile`, and `res.sendFile`
-   3.19.0
    -   Fixed open redirect vulnerability in `express.static`
        ([advisory](https://nodesecurity.io/advisories/serve-static-open-redirect),
        [CVE-2015-1164](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2015-1164)).
-   3.16.10
    -   Fixed directory traversal vulnerabilities in `express.static`.
-   3.16.6
    -   Node.js 0.10 can leak `fd`s in certain situations that affect
        `express.static` and `res.sendfile`. Malicious requests could
        cause `fd`s to leak and eventually lead to `EMFILE` errors and
        server unresponsiveness.
-   3.16.0
    -   Sparse arrays that have extremely high indexes in query string
        could cause the process to run out of memory and crash
        the server.
    -   Extremely nested query string objects could cause the process to
        block and make the server unresponsive temporarily.
-   3.3.0
    -   The 404 response of an unsupported method override attempt was
        susceptible to cross-site scripting attacks.

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
