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

Database integration
====================

Adding the capability to connect databases to Express apps is just a
matter of loading an appropriate Node.js driver for the database in your
app. This document briefly explains how to add and use some of the most
popular Node.js modules for database systems in your Express app:

-   [Cassandra](#cassandra)
-   [Couchbase](#couchbase)
-   [CouchDB](#couchdb)
-   [LevelDB](#leveldb)
-   [MySQL](#mysql)
-   [MongoDB](#mongodb)
-   [Neo4j](#neo4j)
-   [Oracle](#oracle)
-   [PostgreSQL](#postgresql)
-   [Redis](#redis)
-   [SQL Server](#sql-server)
-   [SQLite](#sqlite)
-   [ElasticSearch](#elasticsearch)

<div class="doc-box doc-notice">

These database drivers are among many that are available. For other
options, search on the [npm](https://www.npmjs.com/) site.

</div>

Cassandra
---------

**Module**:
[cassandra-driver](https://github.com/datastax/nodejs-driver)

### Installation

    $ npm install cassandra-driver

### Example

    var cassandra = require('cassandra-driver')
    var client = new cassandra.Client({ contactPoints: ['localhost'] })

    client.execute('select key from system.local', function (err, result) {
      if (err) throw err
      console.log(result.rows[0])
    })

Couchbase
---------

**Module**: [couchnode](https://github.com/couchbase/couchnode)

### Installation

    $ npm install couchbase

### Example

    var couchbase = require('couchbase')
    var bucket = (new couchbase.Cluster('http://localhost:8091')).openBucket('bucketName')

    // add a document to a bucket
    bucket.insert('document-key', { name: 'Matt', shoeSize: 13 }, function (err, result) {
      if (err) {
        console.log(err)
      } else {
        console.log(result)
      }
    })

    // get all documents with shoe size 13
    var n1ql = 'SELECT d.* FROM `bucketName` d WHERE shoeSize = $1'
    var query = N1qlQuery.fromString(n1ql)
    bucket.query(query, [13], function (err, result) {
      if (err) {
        console.log(err)
      } else {
        console.log(result)
      }
    })

CouchDB
-------

**Module**: [nano](https://github.com/dscape/nano)

### Installation

    $ npm install nano

### Example

    var nano = require('nano')('http://localhost:5984')
    nano.db.create('books')
    var books = nano.db.use('books')

    // Insert a book document in the books database
    books.insert({ name: 'The Art of war' }, null, function (err, body) {
      if (err) {
        console.log(err)
      } else {
        console.log(body)
      }
    })

    // Get a list of all books
    books.list(function (err, body) {
      if (err) {
        console.log(err)
      } else {
        console.log(body.rows)
      }
    })

LevelDB
-------

**Module**: [levelup](https://github.com/rvagg/node-levelup)

### Installation

    $ npm install level levelup leveldown

### Example

    var levelup = require('levelup')
    var db = levelup('./mydb')

    db.put('name', 'LevelUP', function (err) {
      if (err) return console.log('Ooops!', err)

      db.get('name', function (err, value) {
        if (err) return console.log('Ooops!', err)

        console.log('name=' + value)
      })
    })

MySQL
-----

**Module**: [mysql](https://github.com/felixge/node-mysql/)

### Installation

    $ npm install mysql

### Example

    var mysql = require('mysql')
    var connection = mysql.createConnection({
      host: 'localhost',
      user: 'dbuser',
      password: 's3kreee7',
      database: 'my_db'
    })

    connection.connect()

    connection.query('SELECT 1 + 1 AS solution', function (err, rows, fields) {
      if (err) throw err

      console.log('The solution is: ', rows[0].solution)
    })

    connection.end()

MongoDB
-------

**Module**: [mongodb](https://github.com/mongodb/node-mongodb-native)

### Installation

    $ npm install mongodb

### Example (v2.\*) {#example-v2}

    var MongoClient = require('mongodb').MongoClient

    MongoClient.connect('mongodb://localhost:27017/animals', function (err, db) {
      if (err) throw err

      db.collection('mammals').find().toArray(function (err, result) {
        if (err) throw err

        console.log(result)
      })
    })

### Example (v3.\*) {#example-v3}

    var MongoClient = require('mongodb').MongoClient

    MongoClient.connect('mongodb://localhost:27017/animals', function (err, client) {
      if (err) throw err

      var db = client.db('animals')

      db.collection('mammals').find().toArray(function (err, result) {
        if (err) throw err

        console.log(result)
      })
    })

If you want an object model driver for MongoDB, look at
[Mongoose](https://github.com/LearnBoost/mongoose).

Neo4j
-----

**Module**: [apoc](https://github.com/hacksparrow/apoc)

### Installation

    $ npm install apoc

### Example

    var apoc = require('apoc')

    apoc.query('match (n) return n').exec().then(
      function (response) {
        console.log(response)
      },
      function (fail) {
        console.log(fail)
      }
    )

Oracle
------

**Module**: [oracledb](https://github.com/oracle/node-oracledb)

### Installation

NOTE: [See installation
prerequisites](https://github.com/oracle/node-oracledb#-installation).

    $ npm install oracledb

### Example

    const oracledb = require('oracledb')
    const config = {
      user: '<your db user>',
      password: '<your db password>',
      connectString: 'localhost:1521/orcl'
    }

    async function getEmployee (empId) {
      let conn

      try {
        conn = await oracledb.getConnection(config)

        const result = await conn.execute(
          'select * from employees where employee_id = :id',
          [empId]
        )

        console.log(result.rows[0])
      } catch (err) {
        console.log('Ouch!', err)
      } finally {
        if (conn) { // conn assignment worked, need to close
          await conn.close()
        }
      }
    }

    getEmployee(101)

PostgreSQL
----------

**Module**: [pg-promise](https://github.com/vitaly-t/pg-promise)

### Installation

    $ npm install pg-promise

### Example

    var pgp = require('pg-promise')(/* options */)
    var db = pgp('postgres://username:password@host:port/database')

    db.one('SELECT $1 AS value', 123)
      .then(function (data) {
        console.log('DATA:', data.value)
      })
      .catch(function (error) {
        console.log('ERROR:', error)
      })

Redis
-----

**Module**: [redis](https://github.com/mranney/node_redis)

### Installation

    $ npm install redis

### Example

    var redis = require('redis')
    var client = redis.createClient()

    client.on('error', function (err) {
      console.log('Error ' + err)
    })

    client.set('string key', 'string val', redis.print)
    client.hset('hash key', 'hashtest 1', 'some value', redis.print)
    client.hset(['hash key', 'hashtest 2', 'some other value'], redis.print)

    client.hkeys('hash key', function (err, replies) {
      console.log(replies.length + ' replies:')

      replies.forEach(function (reply, i) {
        console.log('    ' + i + ': ' + reply)
      })

      client.quit()
    })

SQL Server
----------

**Module**: [tedious](https://github.com/tediousjs/tedious)

### Installation

    $ npm install tedious

### Example

    var Connection = require('tedious').Connection
    var Request = require('tedious').Request

    var config = {
      userName: 'your_username', // update me
      password: 'your_password', // update me
      server: 'localhost'
    }

    var connection = new Connection(config)

    connection.on('connect', function (err) {
      if (err) {
        console.log(err)
      } else {
        executeStatement()
      }
    })

    function executeStatement () {
      request = new Request("select 123, 'hello world'", function (err, rowCount) {
        if (err) {
          console.log(err)
        } else {
          console.log(rowCount + ' rows')
        }
        connection.close()
      })

      request.on('row', function (columns) {
        columns.forEach(function (column) {
          if (column.value === null) {
            console.log('NULL')
          } else {
            console.log(column.value)
          }
        })
      })

      connection.execSql(request)
    }

SQLite
------

**Module**: [sqlite3](https://github.com/mapbox/node-sqlite3)

### Installation

    $ npm install sqlite3

### Example

    var sqlite3 = require('sqlite3').verbose()
    var db = new sqlite3.Database(':memory:')

    db.serialize(function () {
      db.run('CREATE TABLE lorem (info TEXT)')
      var stmt = db.prepare('INSERT INTO lorem VALUES (?)')

      for (var i = 0; i < 10; i++) {
        stmt.run('Ipsum ' + i)
      }

      stmt.finalize()

      db.each('SELECT rowid AS id, info FROM lorem', function (err, row) {
        console.log(row.id + ': ' + row.info)
      })
    })

    db.close()

ElasticSearch
-------------

**Module**: [elasticsearch](https://github.com/elastic/elasticsearch-js)

### Installation

    $ npm install elasticsearch

### Example

    var elasticsearch = require('elasticsearch')
    var client = elasticsearch.Client({
      host: 'localhost:9200'
    })

    client.search({
      index: 'books',
      type: 'book',
      body: {
        query: {
          multi_match: {
            query: 'express js',
            fields: ['title', 'description']
          }
        }
      }
    }).then(function (response) {
      var hits = response.hits.hits
    }, function (error) {
      console.trace(error.message)
    })

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
