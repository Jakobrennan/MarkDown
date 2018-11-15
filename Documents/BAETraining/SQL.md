# Databases 

[SQL](#SQL)
[C.R.U.D](#C.R.U.D)

_Database Def_ - a _database_ is a collection of data that can be **Created**,
**Read**, **Updated**, **Deleted**.


      _Relational DB_                               _Non-Relational DB_
    Relational databases have                    This type of database can be
    relations between their tables.              endless due to the lack of
                                                 relations between the tables.
### SQL

SQL stand for _Structured Query Language_

SQL dependant databases cannot have tables that stray away from the uniformity
of the general data.
For example, a table that consists of first_names, surnames, ages, etc - cannot
have data inputted that is of a different type because it.

As a rule _databases_ usually contian all sorts of information, exptially ones of a _non-relational_ type.

> _Devops_ - Developer operations is a term used in business for a person/team who are the interaction between the operations team and the developers. They're focus is to allow the _developers_ as much time to code and work as possible by dealing with the administration and leg work of other technical and non-technical people.

Whenever you deal with **SQL** you are dealing with 3 languages that deal with data:

| **Data Manipulation Language**                               | **Data Definition Language**                                 | **Data Controlling Language**                                |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| _DML_ Deals with manipulating the the database. Anytime you update or do anything to manipulate the records within the _DB_ you will most likely be using _DML_. | _DDL_ is the _sub-language_ used whenever you are defining/creating or deleting records/data that is going into the _DB_. | _DCL_ is the language that controls the _authorization_ of user's to records, tables and databases. |
| _Keywords:_                                                  | _Keywords:_                                                  | _Keywords:_                                                  |
| **SELECT, INSERT, UPDATE, DELETE**                           | **CREATE, ALTER, DROP**                                      | **GRANT, REVOKE**                                            |

#### Data Types

within _SQL_ there are 3 main types of data that all _DB's_ work with:

- Numeric
- Text
- Date/Time

<u>Numberic</u>

Whenever dealing with _Numberic_ data types, you have 2 options to deal with.

| **Signed**                      | **Unsigned**                     |
|---------------------------------|----------------------------------|
| _signed_ numeric types within _SQL_ ranges between -128 to 128. Usually used whenever you have positive int's to consider | when you have an _unsigned_ numeric type, you have a range between 0 and 240. typically. |

> research the above table as this involved intricate information about computer science and does vary from different flavours of _sql_

<u>Text</u>

_Text_ is anything that contains a _string_ or a _char_. In _SQL_ you will come across _varcahr (variable character)_ which is similar to _char_, the major difference is that you can define the length of your _varchar_

### C.R.U.D

<u>Create</u>

Using _DDL_ you **create** the table and the _Database_. All the keywords explained earlier are used here. 

<u>Read</u>

This part of _C.R.U.D_ uses _DML_, and is literally the part of any _SQL_ language that lets you view the information, be that in a raw form or through **Table Constraints**. _Table Constraints_ are when you make specified queries to the tables/DB's in hopes that in return you'll get the information you want.

<u>Update</u>

Again, here you are using the _DML_ sub-language because you are manipulating the data that is held within the _Database_.

<u>Delete</u>

using the _DDL_ sub-language, this is when you _DROP_ and _DELETE_ the records, tables and databases in your control. 

> Although there is a running joke in most offices, **DROP** _is not a command to be taken lighlty. double think when using it_


Here is a table showing common _C.R.U.D_ funtions in SQL:
|         | **C**     | **R**    | **U**     | **D**     |
|---------|-----------|----------|-----------|-----------|
| **DDL** | _CREATE;_ | _SHOW;_  | _ALTER;_  | _DROP;_   |
| **DML** | _INSERT;_ | _SELECT_ | _UPDATE;_ | _DELETE;_ |



<u>Agreted Functions</u> - These are functions within _SQL_ that allow you to bring data down to a specific value, or retrieve a value of significance. e.g. an _average_, _max_ value, etc.

<u>Correlated Sub-queries</u> -  A query that is within a query, usually within brackets.
