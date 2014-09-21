Variables
=========

What is a variable?
-------------------

Think of variables as a boxes that can hold a value. To store a value in a variable use a `=` sign (this is a called an assignment).

```python
>>> x = 1       # assign the integer value 3 to the variable x
>>> y = 2.5     # assign the float value 4.0 to the variable y
>>> z = '1'     # assign the string '1' to the variable z
>>> x + y       # adding two numbers
3.5
```
> [Try this&nbsp;&rarr; >](https://uvhs-comp.trinket.io/comp1#/variables/variables-part-1)

The name of the variable can be **anything** you want (as long as it follows a few rules):

* Can't begin with a number
* Can't contain spaces or other odd characters
* Can't be a keyword (reserved word)

<span class="label label-success">Have a go</span>: Try this algebra example.

```python
>>> a = 5
>>> b = 2
>>> c = 7
>>> x = a * (b + c)
>>> x
45
```
> [Try this&nbsp;&rarr; >](https://uvhs-comp.trinket.io/comp1#/variables/variables-part-2)

You will often want to save the value an expression evaluates to, so you can use it later in the program.

This can be seen in the algebra example where the result of `a * (b + c)` was assigned to `x`.

Data types
----------

In Python variables can store different types of data. Three common data types are:

> * Integer `int`
> * Float `float`
> * String `str`

Storing these different data types is exactly the same as you saw in the algebra example. You don't have to tell Python what type to store, it figures that out itself.

```python
>>> x = 1       # assign the integer value 3 to the variable x
>>> y = 2.5     # assign the float value 4.0 to the variable y
>>> z = '1'     # assign the string '1' to the variable z
```

You can ask Python what type a variable is using the `type` function.

```python
>>> MyNumber = 3
>>> type(MyNumber)
<type 'int'>
>>> AnotherNumber = 4.0
>>> type(AnotherNumber)
<type 'float'>
>>> TheGreeting = 'hello'
>>> type(TheGreeting)
<type 'str'>
```
> [Try this&nbsp;&rarr; >](https://uvhs-comp.trinket.io/comp1#/variables/data-types-part-1)

### Changing types

To change the type of a variable use the relevant type function: `int`, `float` or `str`.

<span class="label label-success">Have a go</span>: converting string to integer.

```python
>>> Age = "26"
>>> type(Age)
<type 'str'>
>>> Age = int(Age)
>>> type(Age)
<type 'int'>
```
> [Try this&nbsp;&rarr; >](https://uvhs-comp.trinket.io/comp1#/variables/data-types-part-2)

Operators
=========

Artithmetic
-----------

<span class="label label-success">Have a go</span> Use the Python Shell to try out each of these operators:

* `+`
* `-`
* `/`
* `*`
* `//` - integer division
* `%` - remainder after division
* `**` - exponent, first number raised to the power of the second number

### Order of operations

**P E DM AS**

* **P** parentheses
* **E** exponent
* **DM** division and multiplication
* **AS** addition and subtraction

If the operators have same precedence they are evaluated left to right.

`3 - 1 * 2` evaluates to 1 not 4

`6 + 4 / 2` evaluates to 8 not 5

`(6 + 4) / 2` evaluates to 5 not 8


### Example use of `%` and `//`

If you have a variable holding a total number of seconds, however you wanted minutes and seconds. Using `%` and `//` this can easily be calculated.

```python
TotalSeconds = 504
MinutesTaken = TotalSeconds // 60

SecondsTaken = TotalSeconds % 60
```

Other uses could be when converting total hours to a 12/24 hour time, can you think of any others?


Boolean expressions
-------------------

A boolean expression is an expression that Python evaluates to be either `True` or `False`. For example:

```python
>>> 6 > 4
True
```

The standard comparison operators are available to use (note the different style of equal and not equal):

```python
==      # equal to
<       # less than
>       # greater than
<=      # less than or equal to
>=      # greater than or equal to
!=      # not equal to
```
> [Try this&nbsp;&rarr; >](https://uvhs-comp.trinket.io/comp1#/operators/boolean-expressions-part-1)

Boolean operators
-----------------

Using boolean operators, you can join together multiple boolean expressions or negate a result. There are 3 boolean operators in Python:

`and`

`or`

`not`

### How to use them?

Say you want to check a users age and shoe size, used in conjunction with an `if` statement:

```python
Age = int(input("What is your age? "))
ShoeSize = int(input("What is your shoe size? "))

if (Age > 16) and (ShoeSize > 7):
  print("Accepted")
```

print and input
===============

`print` function
----------------

`print` is used to display whatever is inside the brackets of the statement.

```python
>>> print("Hello world")
'Hello world'
```

`print` can also display the value stored in a variable.

```python
>>> Language = "Python"
>>> print(Language)
'Python'
```

### Printing variables

Using `print` you can display messages that include both strings and number values. In a `print` statement you can use `+` or `,` to join together strings and variables.

In this example Python will happily print out the string and the integer on the same line, it will also automatically add a space after the word integer.

```python
>>> AnInt = 43
>>> print("This is an integer", AnInt)
This is an integer 43
```

However, if you were to use a `+` in this example it will cause an error.

```python
>>> AnInt = 43
>>> print("This is an integer " + AnInt)
```

To fix this example, you would need to convert AnInt to a string type. This makes string concatenation work.

```python
>>> AnInt = 43
>>> print("This is an integer " + str(AnInt))
```


`input` function
----------------

The `input` function gets some input from the user. If you save it in to a variable, that variable will have a type - what do you think it will be?

```python
MyInput = input("Type something: ")
type(MyInput)
```

<span class="label label-success">Have a go</span> Try this a few times typing in different responses such as: Barry, 32, 3.14, 1/2/3 etc...

Q) What do you notice about the type of the `MyInput` variable?

A) It is always a `str`, even if you typed in `12` for example.

### Fixing the type problem

If you want to get a number from the user using an `input` statement you will need to be sure to convert the inputted value to a number type (either `int` or `float`).

A common way to do this is to wrap the `input` statement with `int` or `float`.

**Integer example**

```python
>>> MyNumberInput = int(input("Type a number"))
>>> type(MyNumberInput)
<type 'int'>
```

**Float example**

```python
>>> MyNumberInput = float(input("Type a number"))
>>> type(MyNumberInput)
<type 'float'>
```

Selection statements
====================

`if`
----

Sometimes you will want to execute a sequence of statements only if a certain condition is met. For example only print out the secret message if the password is typed in correctly.

**"If the Boolean expression after the `if` keyword evaluates to `True` then the rest of the if statement is executed, else control passes to the next statement."**

This means that if the boolean expression is `True` then code that is indented below is executed otherwise it is skipped over.

In Python a colon `:` is always put at the end of `if` statements. This causes your editor to indent on the next line, indicating that the code you are writing is dependant upon the `if` statement condition above.

```python
Guess = int(input("Guess the number: "))

if (Guess == 42):
    # if guess is correct this code is executed
    print("Well done you guessed correctly.")

# this code will always be executed
print("End of guessing.")
```

There is a weakness in this program, no message is displayed to tell the user they guessed incorrectly. `else` is the solution, keep on reading.

`else`
------

What happens if you want to `print` out a message if the user guesses incorrectly.

```python
Guess = int(input("Guess the number: "))

if (Guess == 42):
    # if guess is correct this code is executed
    print("Well done you guessed correctly.")
else:
    # if guess is incorrect this code is executed
    print("You guess wrong. :(")

# this code will always be executed
print("End of guessing.")
```

`elif`
------




Notes
=====

