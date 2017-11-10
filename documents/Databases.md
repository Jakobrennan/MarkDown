# Databases

## types of databases

* relational database 
* flat file based database
* hierarchal database
* network database
* object-orientated database

## M.E.A.N

`M.E.A.N` is a free `open-source` stack that is usually based around javascript. It contains the main tools and software you need and/or want to create a dynamic web-page. 
**personally, i see this as a kind of framework, you don't have to use these tools as though they are gospel, but unles you know what you are doing, you will have difficulty swapping the tools out and using different software**

>### M - MongoDB (no sql database)
>
>youtube video on how to use and `test` [mongodb](https://www.youtube.com/watch?v=9OPP_1eAENg&list=PL4cUxeGkcC9jpvoYriLI0bY8DOgWZfi6u&index=1)
>
>### E - Express.js ~the web application framework~
>### A - Angular.js ~javascript mvc framework that runs in browser engines~
>### N - Node.js ~execution environment for event-driven server side network applications~
>

---

## Relational Databases

src: [bbc bitesize](http://www.bbc.co.uk/schools/gcsebitesize/ict/databases/2databasesrev2.shtml)

a relational database has more than one table, and the tables are connected using `key fields` (a unique identifier for database records or field entries). 

example of a relational database, if you think of a library database it would have 3 tables:

1. Customer table - when a customer joins the library, information needs to be taken down like the `customer name`, `address` and `unique customer ID`
2. book table - each book needs to be put into the database, information like the `author`, `title` and a `book ID`
3. lending table - when a book is taken by a customer, the `book ID` will be paired with the `unique customer ID` and this will be stored in the database, there may be other information like `date`.


---


## MongoDB

MongoDB is the M in `M.E.A.N` and is written in javascript. It works brilliantly with software that also uses javascript, as they pass information from one to the other extremely well. 
the basic structure of `MongoDB` is like any other databse, the browser sends a request to the *Server*, which processes the request, grabs the information from the *DataBase* and then returns the information to the browser.

>### Mongoose
>mongoose is an extension that you can download with `node.js` that helps with the management of `MongoDB` data.
>For documentation and guides go to [Mongoose](<http://mongoosejs.com/>)


![basicMongoDb](https://i.imgur.com/aBHKFdA.png)







































