#sql databses
##resource - Virtual Academy Microsoft

##Creating a Table

names of tables come in 2 parts:
*Schema* - the title of the general database (for example *Sales*) these will be the general name that is involved with everything in the database
*name* - this will be the name of the table (like *product* for example)

####within tables

each *column* will have a different `Data Type`, and you will define each given `Data Type` by expressing it when you create the table.

```
(productID INTEGER IDENTITY PRIMARY KEY, 
  Name VARCHAR(20),
  Price DECIMAL NULL)  //varying with characters - takes into account the fact that different products will have shorter names than others
```

*ENTER TABLE HERE*

