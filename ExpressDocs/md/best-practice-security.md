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

Production Best Practices: Security
===================================

Overview
--------

The term *“production”* refers to the stage in the software lifecycle
when an application or API is generally available to its end-users or
consumers. In contrast, in the *“development”* stage, you’re still
actively writing and testing code, and the application is not open to
external access. The corresponding system environments are known as
*production* and *development* environments, respectively.

Development and production environments are usually set up differently
and have vastly different requirements. What’s fine in development may
not be acceptable in production. For example, in a development
environment you may want verbose logging of errors for debugging, while
the same behavior can become a security concern in a production
environment. And in development, you don’t need to worry about
scalability, reliability, and performance, while those concerns become
critical in production.

<div class="doc-box doc-info">

**Note**: If you believe you have discovered a security vulnerability in
Express, please see [Security Policies and
Procedures](/en/resources/contributing.html#security-policies-and-procedures).

</div>

Security best practices for Express applications in production include:

-   [Don’t use deprecated or vulnerable versions of
    Express](#dont-use-deprecated-or-vulnerable-versions-of-express)
-   [Use TLS](#use-tls)
-   [Use Helmet](#use-helmet)
-   [Use cookies securely](#use-cookies-securely)
-   [Prevent brute-force attacks against
    authorization](#prevent-brute-force-attacks-against-authorization)
-   [Ensure your dependencies are
    secure](#ensure-your-dependencies-are-secure)
-   [Avoid other known
    vulnerabilities](#avoid-other-known-vulnerabilities)
-   [Additional considerations](#additional-considerations)

Don’t use deprecated or vulnerable versions of Express
------------------------------------------------------

Express 2.x and 3.x are no longer maintained. Security and performance
issues in these versions won’t be fixed. Do not use them! If you haven’t
moved to version 4, follow the [migration
guide](/en/guide/migrating-4.html).

Also ensure you are not using any of the vulnerable Express versions
listed on the [Security updates
page](/en/advanced/security-updates.html). If you are, update to one of
the stable releases, preferably the latest.

Use TLS
-------

If your app deals with or transmits sensitive data, use [Transport Layer
Security](https://en.wikipedia.org/wiki/Transport_Layer_Security) (TLS)
to secure the connection and the data. This technology encrypts data
before it is sent from the client to the server, thus preventing some
common (and easy) hacks. Although Ajax and POST requests might not be
visibly obvious and seem “hidden” in browsers, their network traffic is
vulnerable to [packet
sniffing](https://en.wikipedia.org/wiki/Packet_analyzer) and
[man-in-the-middle
attacks](https://en.wikipedia.org/wiki/Man-in-the-middle_attack).

You may be familiar with Secure Socket Layer (SSL) encryption. [TLS is
simply the next progression of
SSL](https://msdn.microsoft.com/en-us/library/windows/desktop/aa380515(v=vs.85).aspx).
In other words, if you were using SSL before, consider upgrading to TLS.
In general, we recommend Nginx to handle TLS. For a good reference to
configure TLS on Nginx (and other servers), see [Recommended Server
Configurations (Mozilla
Wiki)](https://wiki.mozilla.org/Security/Server_Side_TLS#Recommended_Server_Configurations).

Also, a handy tool to get a free TLS certificate is [Let’s
Encrypt](https://letsencrypt.org/about/), a free, automated, and open
certificate authority (CA) provided by the [Internet Security Research
Group (ISRG)](https://letsencrypt.org/isrg/).

Use Helmet
----------

[Helmet](https://www.npmjs.com/package/helmet) can help protect your app
from some well-known web vulnerabilities by setting HTTP headers
appropriately.

Helmet is actually just a collection of smaller middleware functions
that set security-related HTTP response headers:

-   [csp](https://github.com/helmetjs/csp) sets the
    `Content-Security-Policy` header to help prevent cross-site
    scripting attacks and other cross-site injections.
-   [hidePoweredBy](https://github.com/helmetjs/hide-powered-by) removes
    the `X-Powered-By` header.
-   [hpkp](https://github.com/helmetjs/hpkp) Adds [Public Key
    Pinning](https://developer.mozilla.org/en-US/docs/Web/Security/Public_Key_Pinning)
    headers to prevent man-in-the-middle attacks with
    forged certificates.
-   [hsts](https://github.com/helmetjs/hsts) sets
    `Strict-Transport-Security` header that enforces secure (HTTP
    over SSL/TLS) connections to the server.
-   [ieNoOpen](https://github.com/helmetjs/ienoopen) sets
    `X-Download-Options` for IE8+.
-   [noCache](https://github.com/helmetjs/nocache) sets `Cache-Control`
    and Pragma headers to disable client-side caching.
-   [noSniff](https://github.com/helmetjs/dont-sniff-mimetype) sets
    `X-Content-Type-Options` to prevent browsers from MIME-sniffing a
    response away from the declared content-type.
-   [frameguard](https://github.com/helmetjs/frameguard) sets the
    `X-Frame-Options` header to provide
    [clickjacking](https://www.owasp.org/index.php/Clickjacking) protection.
-   [xssFilter](https://github.com/helmetjs/x-xss-protection) sets
    `X-XSS-Protection` to enable the Cross-site scripting (XSS) filter
    in most recent web browsers.

Install Helmet like any other module:

    $ npm install --save helmet

Then to use it in your code:

    // ...

    var helmet = require('helmet')
    app.use(helmet())

    // ...

### At a minimum, disable X-Powered-By header

If you don’t want to use Helmet, then at least disable the
`X-Powered-By` header. Attackers can use this header (which is enabled
by default) to detect apps running Express and then launch
specifically-targeted attacks.

So, best practice is to to turn off the header with the `app.disable()`
method:

    app.disable('x-powered-by')

If you use `helmet.js`, it takes care of this for you.

<div class="doc-box doc-info">

**Note**: Disabling the `X-Powered-By header` does not prevent a
sophisticated attacker from determining that an app is running Express.
It may discourage a casual exploit, but there are other ways to
determine an app is running Express.

</div>

Use cookies securely
--------------------

To ensure cookies don’t open your app to exploits, don’t use the default
session cookie name and set cookie security options appropriately.

There are two main middleware cookie session modules:

-   [express-session](https://www.npmjs.com/package/express-session)
    that replaces `express.session` middleware built-in to Express 3.x.
-   [cookie-session](https://www.npmjs.com/package/cookie-session) that
    replaces `express.cookieSession` middleware built-in to Express 3.x.

The main difference between these two modules is how they save cookie
session data. The
[express-session](https://www.npmjs.com/package/express-session)
middleware stores session data on the server; it only saves the session
ID in the cookie itself, not session data. By default, it uses in-memory
storage and is not designed for a production environment. In production,
you’ll need to set up a scalable session-store; see the list of
[compatible session
stores](https://github.com/expressjs/session#compatible-session-stores).

In contrast,
[cookie-session](https://www.npmjs.com/package/cookie-session)
middleware implements cookie-backed storage: it serializes the entire
session to the cookie, rather than just a session key. Only use it when
session data is relatively small and easily encoded as primitive values
(rather than objects). Although browsers are supposed to support at
least 4096 bytes per cookie, to ensure you don’t exceed the limit, don’t
exceed a size of 4093 bytes per domain. Also, be aware that the cookie
data will be visible to the client, so if there is any reason to keep it
secure or obscure, then express-session may be a better choice.

### Don’t use the default session cookie name

Using the default session cookie name can open your app to attacks. The
security issue posed is similar to `X-Powered-By`: a potential attacker
can use it to fingerprint the server and target attacks accordingly.

To avoid this problem, use generic cookie names; for example using
[express-session](https://www.npmjs.com/package/express-session)
middleware:

    var session = require('express-session')
    app.set('trust proxy', 1) // trust first proxy
    app.use(session({
      secret: 's3Cur3',
      name: 'sessionId'
    }))

### Set cookie security options

Set the following cookie options to enhance security:

-   `secure` - Ensures the browser only sends the cookie over HTTPS.
-   `httpOnly` - Ensures the cookie is sent only over HTTP(S), not
    client JavaScript, helping to protect against cross-site
    scripting attacks.
-   `domain` - indicates the domain of the cookie; use it to compare
    against the domain of the server in which the URL is
    being requested. If they match, then check the path attribute next.
-   `path` - indicates the path of the cookie; use it to compare against
    the request path. If this and domain match, then send the cookie in
    the request.
-   `expires` - use to set expiration date for persistent cookies.

Here is an example using
[cookie-session](https://www.npmjs.com/package/cookie-session)
middleware:

    var session = require('cookie-session')
    var express = require('express')
    var app = express()

    var expiryDate = new Date(Date.now() + 60 * 60 * 1000) // 1 hour
    app.use(session({
      name: 'session',
      keys: ['key1', 'key2'],
      cookie: {
        secure: true,
        httpOnly: true,
        domain: 'example.com',
        path: 'foo/bar',
        expires: expiryDate
      }
    }))

Prevent brute-force attacks against authorization
-------------------------------------------------

Make sure login endpoints are protected to make private data more
secure.

A simple and powerful technique is to block authorization attempts using
two metrics:

1.  The first is number of consecutive failed attempts by the same user
    name and IP address.
2.  The second is number of failed attempts from an IP address over some
    long period of time. For example, block an IP address if it makes
    100 failed attempts in one day.

[rate-limiter-flexible](https://github.com/animir/node-rate-limiter-flexible)
package provides tools to make this technique easy and fast. You can
find [an example of brute-force protection in the
documentation](https://github.com/animir/node-rate-limiter-flexible/wiki/Overall-example#login-endpoint-protection)

Ensure your dependencies are secure
-----------------------------------

Using npm to manage your application’s dependencies is powerful and
convenient. But the packages that you use may contain critical security
vulnerabilities that could also affect your application. The security of
your app is only as strong as the “weakest link” in your dependencies.

Since npm@6, npm automatically reviews every install request. Also you
can use ‘npm audit’ to analyze your dependency tree.

    $ npm audit

If you want to stay more secure, consider [Snyk](https://snyk.io/).

Snyk offers both a [command-line
tool](https://www.npmjs.com/package/snyk) and a [Github
integration](https://snyk.io/docs/github) that checks your application
against [Snyk’s open source vulnerability
database](https://snyk.io/vuln/) for any known vulnerabilities in your
dependencies. Install the CLI as follows:

    $ npm install -g snyk
    $ cd your-app

Use this command to test your application for vulnerabilities:

    $ snyk test

Use this command to open a wizard that walks you through the process of
applying updates or patches to fix the vulnerabilities that were found:

    $ snyk wizard

Avoid other known vulnerabilities
---------------------------------

Keep an eye out for [Node Security
Project](https://nodesecurity.io/advisories) or
[Snyk](https://snyk.io/vuln/) advisories that may affect Express or
other modules that your app uses. In general, these databases are
excellent resources for knowledge and tools about Node security.

Finally, Express apps - like any other web apps - can be vulnerable to a
variety of web-based attacks. Familiarize yourself with known [web
vulnerabilities](https://www.owasp.org/index.php/Top_10-2017_Top_10) and
take precautions to avoid them.

Additional considerations
-------------------------

Here are some further recommendations from the excellent [Node.js
Security
Checklist](https://blog.risingstack.com/node-js-security-checklist/).
Refer to that blog post for all the details on these recommendations:

-   Use [csurf](https://www.npmjs.com/package/csurf) middleware to
    protect against cross-site request forgery (CSRF).
-   Always filter and sanitize user input to protect against cross-site
    scripting (XSS) and command injection attacks.
-   Defend against SQL injection attacks by using parameterized queries
    or prepared statements.
-   Use the open-source [sqlmap](http://sqlmap.org/) tool to detect SQL
    injection vulnerabilities in your app.
-   Use the [nmap](https://nmap.org/) and
    [sslyze](https://github.com/nabla-c0d3/sslyze) tools to test the
    configuration of your SSL ciphers, keys, and renegotiation as well
    as the validity of your certificate.
-   Use [safe-regex](https://www.npmjs.com/package/safe-regex) to ensure
    your regular expressions are not susceptible to [regular expression
    denial of
    service](https://www.owasp.org/index.php/Regular_expression_Denial_of_Service_-_ReDoS) attacks.

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
