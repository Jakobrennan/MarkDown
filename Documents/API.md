# wiki info

## API

The basic premis of why you have API's.
Every website has to get information from a  web server, and still, there are some tasks that can be quite time consuming for a server to complete. e.g. if you are on a website and you want the name and address from someone in a phone book. If that phone book has 10 people in it, then it will be easy for the website to load, all the information, and for you to search for it.
However, if the phone book has 10,000 people, then the loading of the website is going to take some time.

An API can take your request, attach it to the web-page, the web-page then sends the code to the server, and the server replies with only the data you requested, not the remaining 9,000.

![](https://cdn.zapier.com/storage/photos/73c10a4db7511d53234d673e9b37aaf9.png)



API's are implemented on the server side of any website that you create. It is one half of the 2 parts. the `Server` side where the API is, and the `Client` side, which is where the user on the website makes the request to the `Server`. 


### HTTP requests

hyper-text transfer protocol is something that is all around the Internet, and has it's own set of documentation that allows you to incorporate an API into the web request. 

![](https://cdn.zapier.com/storage/photos/9ec65c79de8ae54080c1b417540469a6.png)

HTTP works like a basic `request - respond` set and is simple to understand, `client` contacts `server`, `server` repsond to `client`.
but HTTP needs 4 thing:
1. **URL** (uniform resource locater)
2. **Method****
3. List of **Headers**
4. **Body**


> #### URL
>
> URL is something that allows you to get an image, web-page, video, direction, definition, search, song from the internet. API's call URL's `resources`, and, where > as a URL would have a link to a webisite, and API extends this idea and allows you to get tweets, youtube comments, products, customer info, etc.
>
>
> #### Method
>
> also takes the name `verb` the method has four different types:
>
> * `GET` - Asks the server to retrieve a resource
> * `POST` - Asks the server to create a new resource
> * `PUT` - Asks the server edit/update an existing resource
> * `DELETE` -Asks the server to delete a resource
>
>
> #### Headers
>
> Headers are basically meta-data inside a web-page. Usually found within the `\<head\>` of a website, and this gives the `server` information about the `client` and > the device that is being used. For example, HTTP have a `header` called "User-Agent" that tells the `server` the device making the request is a mobile device, and > will change the size of the website to suit the mobile device.
>
>
> #### Body
>
> **this is the only part of the request that the `client` has complete control over**
> The body is essentially all of the information about the client and it also contains the location of where the information is going. 
>


That covers the four aspects of HTTP Requests.

![](https://cdn.zapier.com/storage/photos/4717d012f26dc6a4928e0d025102af7f.png)



---

# Rest API

"*All REST are a form of API, but not all API is REST...*" - someone on stack overflow

before REST there was something called SOAP (Simple Object Access Protocol).

### SOAP used standardized protocols and WSDL files

SOAP is a standardized protocol that requires `.xml` as the message format. as a standardized protocol the message formar is defined through `WSDL (Web Services Description Language)`.
The `WSDL` allows attributes and elements of a message to exhange between servers and hardware that are carrying the message.

SOAP's messages are enclosed within an *envelope* which consists of a `body` and a `header`. 

**Problems with SOAP**
the biggest problems with SOAP is the message format is too verbose and heavy. The bandwidth demand tends to crash mobile services and devices that cannot handle a lot of data.

## REST (REpresentational State Transfer)

`REST` is a *style* not a **standard**. This is important to remember. 
`REST` uses HTTP as the transport protocol, but unlike SOAP, `REST` is an architecural style and not a standard protocol. (this is why it's called `RESTful` API and not `REST` API, because it doesn't meet the standard set out by [Dr. Roy Fielding](https://en.wikipedia.org/wiki/Roy_Fielding))

### Requests and Responses

Here is a layout of the REST API Model:


![](http://idratherbewriting.com/learnapidoc/images/restapi_restapi.png)



`REST` supports any message format, but must use HTTP as the transporting protocol to contact the servers and such. 
the format's `REST` support include:
* html
* xml
* json
* atom
* rss
* csv
* and a few more

JSON is the most preferred choice amongst developers due to it's agility and flexible message formatting. JSON is also lightweight and proves to be the quickest option amongst all of the options.


### a few examples

here is the structure for a basic website Request and Response between a browser and a server:

![](http://idratherbewriting.com/learnapidoc/images/restapi_www.svg)

Most of the web uses the `RESTful` style API structure, here are some example REST URI's:

> http://apiserver.com/homes?limit=5&format=json

This retrieves the first 5 resources on the web-page 'home', then displays that information in a 'JSON' format.

> http://apiserver.com/homes/1234

This URI retrieves that resource with the ID of '1234'


## REST `Stateless`-ness and `Cache`-ability

 `stateless` - This basically means everytime you make a request using `REST API`, the `endpoint` does not take into acount your previous requests, becuase it doesnt remember your previous requests. Each request is treated as it's own request, and not an *add on* of the previous one.
 
 `cache` - this is used in the exact same way that webpage caching is used. when you make a request, the `browser` uses the *last-modified-time* value in the `HTTP` headers to if it needs to get this *resource* again. if the content hasn't been modified since the last visit, then the browser will use this file instead of retrieving the new file. This boost's permormance massively.
 
 `REST API` has a lot more features like `HATEOAS` (Hypermedia As The Engine of Application State). your can see them on the [REST API Tutorial](http://www.restapitutorial.com/lessons/whatisrest.html).
 
 
---

# Node.js `Express` framework and `RESTful` API support

## `Express`

Express is a web app `framework` that provides robust and dynamic features for web and mobile application development. here are some key features that `Express` support:
* allowing `middlewares` to respond to `HTTP requests`
* defines routing tables used to perform different actions based on `HTTP methods` and `URL`
* allowing dynamically rendered HTML pages to be created based on passing arguments to templates

### quick installation guide to node.js

firstly, install `Express` as a global variable within a file structure.

```bash
$ npm install express --save
```

then download these modules to help support the creation of the API:

```bash
$ npm install body-parser --save
$ npm install cookie-parser --save
$ npm install multr --save
```

- body parser - this is a `middleware` that handles JSON, RAW, TEXT and URL encoded data.
- cookie parser - parse cookie header and populate req.cookies with an object keyed by the cookie name.
- multr - this is a node.js middleware for handling multipart/form-data.

## Hello World from node.js

this is the basic code for a `hello world` program using the `Express` Framework, listening on port 8081.

```javascript
var expres = require('express');
var app = express();

app.get('/', function (req, res) {
  res.send('Hello World!');
})

var erver = app.listen(8081, function() {
  var host = server.address().address
  var port = server.address().port
  
  console.log("Example app listening at http://%s:%s", host, port)
})
```

save this code in a file called `server.js` then locate that file in a command terminal. type the following code:

```bash
$ npm server.js
```

this should be the output:

```bash
Example app listening at http://0.0.0.0:8081
```

now, in a `browser` type `http://127.0.0.1:8081`

walla!


## 





















