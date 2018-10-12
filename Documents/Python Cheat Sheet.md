# Python Cheat Sheet

[In-built functions](#In-built functions)

[Common Operators](#Common Operators)

[Comparison Operators](#Comparison Operators)

[Binary Boolean Operators](#Binary Boolean Operators)

[Conditional Statements](#Conditional Statements)

[Loop Statements](#Loop Statements)

#### In-built functions

`print()` - print is what allows you to print your variables, strings, intergers, floating points etc, to the screen when you are writing a program in Python.

`len()` - prints the length of the probided parameter, variable, expression.

`str()` - converts the provided parameter into a string.

`float()` - converts the provided parameter into a float. **You cannot convert a `string` to a `float`**

`int()` - converst the provided parameter into an integer.

> you cannot covert a **string** to and **integer**
>
> when converting a **float** to an **Int**, python will round the **_down_**  to the nearest whole number.

`input()` - this function accepts input from the user, commonly used to assign a value to a variable. **input() always returns a string format**

> It is possible to **typecast** the `input()` function to the data-type you want.

`*` - you can apply this operator to string data types, the result will be that string multiplied by the integer and concatonated into a string again. (example, `pam = 'string' | pam * 3 | pam = 'stringstringstring')

`+` - when you apply this operator to a string, you will have a concatonated string as a result.

`rount()` - rounds the provided parameter as to the nearst whole number, (2.5 to 3, 2.2 to 2). The output of this module is a `floating point` data type. **you can acquire and `int` data type by typecasting with `int()` module**

`import` - keyword that _must_ be used in order to use any modules from python's standard library

`from ... import *` - alternative way to import modules. You don't need the prefix with this method but it ruins readability.



---

#### Common Operators

| operators | Description                             |
| --------- | --------------------------------------- |
| **        | Indeces                                 |
| *         | Multiply                                |
| %         | Modular                                 |
| //        | Integer division/floored quotientDivide |
| /         | Divide                                  |
| +         | Add                                     |
| -         | Subtract                                |

> python follows the BODMAS mathematical logic

You can develop a script or program in python, or you can write python straight into the terminal using the `python` shell tool. In order to use the tool, download the engine from _le web_ and type `python` into your terminal or command line, you should see something like the following

```python
Python 2.7.12 (default, Dec  4 2017, 14:50:18) 
[GCC 5.4.0 20160609] on linux2
Type "help", "copyright", "credits" or "license" for more information.
>>> 
```

---

#### Comparison Operators

| Operators | Description              |
| --------- | ------------------------ |
| ==        | Equal to                 |
| !=        | Not equal to             |
| >         | Greater than             |
| <         | Less than                |
| >=        | Greater than or equal to |
| <=        | Less than or equal to    |

---

#### Binary Boolean Operators

| operators | Description                                             |
| --------- | ------------------------------------------------------- |
| _and_     | returns `True` only if both calues are true             |
| _or_      | returns `True` if either part of the expression is true |
| _not_     | converts the value to it's opposite (not True = false)  |
| _xor_     |                                                         |

> the priority of the vlaues is; `not` -> `and` -> `or`

---

#### Conditional Statements

| statement    | Description                                                  |
| ------------ | ------------------------------------------------------------ |
| _if ... :_   | Prints the following code if the defined statement is `True` |
| _else:_      | Prints the code if the statement for the `if` is `False`     |
| _elif ... :_ | If the `if` condition returns false, the `elif` allows you to input another condition. |

---

#### Loop Statements

| statement     | Description                                                  |
| ------------- | ------------------------------------------------------------ |
| _if ... :_    | Although a conditional statement, when the logic is applied properly, an `if` can be a loop too |
| _while ... :_ | when the condition of the `while` statement is `True`, the block of code is run |
| _break_       | When a `break` is met in a block of code, the **_`execution`_** is sent to the end of the block |
| _continue_    | when a `continue` is met in a block of code, the **_`execution`_** is sent to the start of the block |
| for ... :     | loops through the block of code however many times you express |

> _for i in range(**a**, **b**, **c**):_
>
> The snippet above has 3 things to consider when using _ints_ as a parameter of a _range()_ - _a_ = the starting point, _b_ = the end point, and _c_ = the increments between _a_ and _b_ 

---

