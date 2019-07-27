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

Health Checks and Graceful Shutdown
===================================

Graceful shutdown
-----------------

When you deploy a new version of your application, you must replace the
previous version. The [process manager](pm.html) you’re using will first
send a SIGTERM signal to the application to notify it that it will be
killed. Once the application gets this signal, it will stop accepting
new requests, finish all the ongoing requests, and clean up the
resources it used, including database connections and file locks.

Health checks
-------------

A load balancer uses health checks to determine if an application
instance is healthy and can accept requests. For example, [Kubernetes
has two health
checks](https://kubernetes.io/docs/tasks/configure-pod-container/configure-liveness-readiness-probes/):

-   `liveness`, that determines when to restart a container.
-   `readiness`, that determines when a container is ready to start
    accepting traffic. When a pod is not ready, it is removed from the
    service load balancers.

Third-party solutions
---------------------

<div class="doc-box doc-warn">

**Warning**: This information refers to third-party sites, products, or
modules that are not maintained by the Expressjs team. Listing here does
not constitute an endorsement or recommendation from the Expressjs
project team.

</div>

### Terminus

[Terminus](https://github.com/godaddy/terminus) is an open-source
project that adds health checks and graceful shutdown to your
application to eliminate the need to write boilerplate code. You just
provide the cleanup logic for graceful shutdowns and the health check
logic for health checks, and terminus handles the rest.

Install terminus as follows:

    npm i @godaddy/terminus --save

Here’s a basic template that illustrates using terminus. For more
information, see <https://github.com/godaddy/terminus>.

    const http = require('http')
    const express = require('express')
    const terminus = require('@godaddy/terminus')

    const app = express()

    app.get('/', (req, res) => {
      res.send('ok')
    })

    const server = http.createServer(app)

    function onSignal () {
      console.log('server is starting cleanup')
      // start cleanup of resource, like databases or file descriptors
    }

    async function onHealthCheck () {
      // checks if the system is healthy, like the db connection is live
      // resolves, if health, rejects if not
    }

    terminus(server, {
      signal: 'SIGINT',
      healthChecks: { '/healthcheck': onHealthCheck },
      onSignal
    })

    server.listen(3000)

### Lightship

[Lightship](https://github.com/gajus/lightship) is an open-source
project that adds health, readiness and liveness checks to your
application. Lightship is a standalone HTTP-service that runs as a
separate HTTP service; this allows having health-readiness-liveness HTTP
endpoints without exposing them on the public interface.

Install Lightship as follows:

    npm install lightship

Basic template that illustrates using Lightship:

    const http = require('http')
    const express = require('express')
    const {
      createLightship
    } = require('lightship')

    // Lightship will start a HTTP service on port 9000.
    const lightship = createLightship()

    const app = express()

    app.get('/', (req, res) => {
      res.send('ok')
    })

    app.listen(3000, () => {
      lightship.signalReady()
    })

    // You can signal that the service is not ready using `lightship.signalNotReady()`.

[Lightship documentation](https://github.com/gajus/lightship) provides
examples of the corresponding [Kubernetes
configuration](https://github.com/gajus/lightship#lightship-usage-kubernetes-container-probe-configuration)
and a complete example of integration with
[Express.js](https://github.com/gajus/lightship#using-with-expressjs).

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
