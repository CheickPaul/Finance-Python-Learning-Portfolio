
# Lesson 1: Constants, Reserved Words, Variables

This lesson explains three important basic elements in Python: **constants**, **reserved words**, and **variables**. These are some of the small building blocks that appear in almost every Python program. This lesson also introduces the idea of **assignment**, which is how Python stores values in memory and updates them later.

## Constants

A **constant** is a fixed value written directly in the code.

Examples:

- **"123"**
- **"98.6"**
- **"'Hello world'"**

Constants are called constants because their value does not change.

There are different types of constants in Python:

- an **integer constant** is a whole number like **"123"**
- a **floating-point constant** is a decimal number like **"98.6"**
- a **string constant** is text written between quotes like **"'Hello world'"**

String constants are useful when a program needs to display text to the user.

## Reserved Words

Python has special words that already have a meaning in the language. These are called **reserved words**.

Examples:

- **"class"**
- **"def"**
- **"if"**
- **"else"**
- **"lambda"**
- **"from"**
- **"break"**

You must not use these words as:

- variable names
- function names
- class names

Python expects these words to keep their special meaning.

## Variables

A **variable** is a name chosen by the programmer to store a value.

A variable works like a label attached to a place in memory.

Example:

"x = 12.2"

This means:

- Python creates a place in memory
- gives it the name **"x"**
- stores **12.2** inside it

Later, the value can be changed:

"x = 100"

The variable name stays the same, but the value inside it changes.

Variables are useful because they let a program remember information and update it when needed.

## Variable Name Rules

Python has rules for variable names.

A variable name can:

- start with a **letter**
- start with an **underscore**
- contain **letters**
- contain **numbers**
- contain **underscores**

Examples of valid variable names:

- **"spam"**
- **"eggs"**
- **"spam23"**
- **"_temp"**

Examples of invalid variable names:

- **"23spam"** → cannot start with a number
- **"#value"** → special characters are not allowed
- **"name!"** → special characters are not allowed

In general, simple lowercase variable names are easier to read.

## Case Sensitivity

Python is **case-sensitive**.

This means these are all different variable names:

- **"spam"**
- **"Spam"**
- **"SPAM"**

Python treats them as separate variables.

Even if this is allowed, it is not a good habit because it can confuse the reader.

## Assignment

The **assignment statement** gives a value to a variable.

Example:

"x = 2"

This stores **2** in **"x"**.

You can also use a variable on the right side of an assignment.

Example:

"x = x + 2"

This means:

- take the current value of **"x"**
- add **2**
- store the result back into **"x"**

If **"x"** was **2**, it becomes **4**.

## What this lesson does

- explains what **constants** are
- explains what **reserved words** are
- explains what **variables** are
- shows how **assignment** works
- shows how a variable can change value

## What I learn from this lesson

- how to identify **integer**, **floating-point**, and **string** constants
- what rules must be followed when naming variables
- that Python is **case-sensitive**

  ---
  #  Lesson 2: Numerical Expressions

In this lesson, we continue working with the **right-hand side of assignment statements** and learn more about **numerical expressions** in Python. Numerical expressions are combinations of numbers, variables, and operators that Python evaluates to produce a result.

Python uses special symbols for mathematical operations because programming languages were designed around the characters available on early computer keyboards. That is why some operators look different from standard mathematical notation.

## Operators

Python uses the following numeric operators:

- **"+"** for addition
- **"-"** for subtraction
- **"*"** for multiplication
- **"/"** for division
- **"**"** for exponentiation
- **"%"** for remainder or modulo

These operators are used to build numerical expressions.

### "+"
The **"+"** operator adds two values together.

### "-"
The **"-"** operator subtracts one value from another.

### "*"
The **"*"** operator multiplies two values.

### "/"
The **"/"** operator divides one value by another.

### "**"
The **"**"** operator means **power** or **exponentiation**.

Example:

"4 ** 3"

This means:

"4 * 4 * 4"

So the result is:

"64"

### "%"
The **"%"** operator gives the **remainder** after division. This is called the **modulo** operator.

Example:

"23 % 5"

If you divide 23 by 5:

- 5 goes into 23 four times
- 4 × 5 = 20
- the remainder is 3

So:

"23 % 5"

gives:

"3"

## Why modulo is useful

The modulo operator is very useful in programming.

For example:

- to check if a number is **even or odd**
- to keep a number within a certain range
- to simulate things like **dice rolls**
- to choose an item from a fixed group, like one card from 52 cards

Example:

"10 % 2"

This gives:

"0"

So 10 is even.

Example:

"11 % 2"

This gives:

"1"

So 11 is odd.

## Order of operations

Python follows rules to decide the order in which parts of an expression are evaluated.

This is called the **order of operations**.

The order is:

1. **Parentheses**
2. **Exponentiation**
3. **Multiplication, Division, Modulo**
4. **Addition, Subtraction**
5. **Left to right** when operators have the same priority


So the result is:

"9"

Parentheses make expressions easier to read and avoid confusion.

## Exponentiation before multiplication

## Multiplication and division before addition

## Left to right rule

## Why parentheses are helpful

Even when Python already knows the correct order, many programmers still use parentheses because they make the code easier for humans to read.

For example:

"1 + 2 * 3"

works fine, but this is often easier to read:

"1 + (2 * 3)"

Parentheses make the intention clearer.

## What this lesson does

- introduces **numerical expressions**
- explains the main numeric operators in Python
- shows how **addition**, **subtraction**, **multiplication**, **division**, **power**, and **modulo** work
- explains the **modulo operator**
- introduces the **order of operations**
- shows why **parentheses** are useful
- explains how Python evaluates expressions step by step

## What I learn from this lesson

- how to write numerical expressions in Python
- what the operators **"+"**, **"-"**, **"*"**, **"/"**, **"**"**, and **"%"** mean
- how the **modulo** operator works
- why modulo is useful in programming
- that Python follows an **order of operations**
- that **parentheses** are evaluated first
- that operators with the same priority are evaluated **left to right**
- how to break down a complex expression step by step

  ---

  # Lesson 3: Variable Types

In this lesson, we continue learning about **variables**, **constants**, and **expressions**, but now we focus on an important new idea: **type**. In Python, every value has a type. Python does not only remember the value stored in a variable, it also remembers what kind of value it is.

A value can be:

- an **integer**
- a **floating-point number**
- a **string**

This matters because Python does not treat all values in the same way. The same operator can behave differently depending on the type of the values it is working with.

## Code

"ddd = 1 + 4"

"print(ddd)"

"eee = 'hello ' + 'there'"

"print(eee)"

## Explanation

### Python keeps track of types

Python always keeps track of two things:

- the **value**
- the **type** of the value

For example:

- **"1"** is an integer
- **"98.6"** is a floating-point number
- **"'hello'"** is a string

This is important because some operations work only with certain types.

## The "+" operator depends on type

The **"+"** operator can do different things depending on the type of its operands.

Example with integers:

"ddd = 1 + 4"

Here, Python sees two integers:

- **"1"**
- **"4"**

Since both are integers, Python performs **addition**.

So the result is:

"5"

Example with strings:

"eee = 'hello ' + 'there'"

Here, Python sees two strings:

- **"'hello '"**
- **"'there'"**

So instead of adding numbers, Python **concatenates** the strings.

The result is:

"'hello there'"

Notice that the space in **"'hello '"** is written inside the first string. The **"+"** operator does not add spaces automatically.

## Type errors

If you try to combine values of different types in a way Python does not understand, Python stops with an error.

Example:

"eee = 'hello ' + 'there'"

"eee = eee + 1"

In this case:

- **"eee"** is a string
- **"1"** is an integer

Python does not know how to add a string and an integer together, so it stops and shows a **TypeError**.

## What a traceback means

When Python cannot understand an instruction, it shows a **traceback**.

A traceback means:

- Python found a problem
- Python stopped running the program
- Python tells you where the problem happened
- Python tells you what kind of error it found

This is not Python saying you are a bad programmer.

It is simply Python saying:

- I do not know how to do this
- please fix this instruction

So a traceback is actually helpful because it gives clues about:

- where Python got lost
- what kind of mistake happened

## The `type()` function

Python has a built-in function called **"type()"** that tells you the type of a value or a variable.

Example:

"type(eee)"

If **"eee"** contains a string, Python will tell you that it is a **string**.

More examples:

"type('hello')"

"type(1)"

The first one is a **string**.  
The second one is an **integer**.

This function is very useful when you are confused about what kind of value a variable contains.

## Integer and floating-point numbers

There are two main numeric types in Python:

- **integers**
- **floating-point numbers**

An **integer** has no decimal point.

Examples:

- **"1"**
- **"42"**
- **"1000"**

A **floating-point number** has a decimal point.

Examples:

- **"98.6"**
- **"42.0"**
- **"3.14"**

Even if the number looks whole, like **"42.0"**, it is still a float because it has a decimal point.

## Difference between integers and floats

Integers and floating-point numbers are stored differently inside Python.

In general:

- **integers** are exact
- **floats** can represent a wider range of values
- **floats** are not always perfectly precise

That is why floats are useful for things like:

- temperature
- speed
- measurements

But floats are not ideal for exact money calculations.

## Converting types

Python has built-in functions to convert one type to another.

The two important ones here are:

- **"float()"**
- **"int()"**

### `float()`

Example:

"print(float(99) + 100)"

Here, Python converts **"99"** to **"99.0"**.

Then it adds:

"99.0 + 100"

The result is:

"199.0"

Because one of the values is a float, the result is also a float.

Another example:

"i = 42"

"f = float(i)"

Now:

- **"i"** is an integer
- **"f"** is a float

### `int()`

The **"int()"** function converts a value to an integer when possible.

Example:

"sval = '123'"

"ival = int(sval)"

Now **"ival"** contains the integer **123** instead of the string **'123'**.

That means you can now do arithmetic with it.

Example:

"ival = int('123')"

"print(ival + 1)"

This prints:

"124"

## Strings that contain digits

Sometimes data comes from outside the program as text.

For example:

"'123'"

This looks like a number, but it is really a **string** because it is inside quotes.

Python sees it as three characters:

- **"1"**
- **"2"**
- **"3"**

If you try this:

"sval = '123'"

"print(sval + 1)"

Python gives an error, because **"sval"** is still a string.

But if you convert it first:

"ival = int(sval)"

"print(ival + 1)"

then Python is happy.

## Invalid conversion

If the string does not actually contain digits, conversion fails.

Example:

"int('hello')"

Python cannot convert **"'hello'"** into an integer, so it stops with an error.

This is another case where Python gives a traceback to explain that the conversion is invalid.

## Division in Python 3

In Python 3, division always produces a floating-point result.

Example:

"10 / 2"

This gives:

"5.0"

Example:

"9 / 2"

This gives:

"4.5"

Example:

"99 / 100"

This gives:

"0.99"

This is different from older Python 2 behavior, where integer division sometimes removed the decimal part.

Python 3 makes division behave more naturally.

## Input from the keyboard

Python can also read data from the user with the **"input()"** function.

Example:

"nam = input('Who are you? ')"

"print('Welcome', nam)"

Here is what happens:

- Python prints the prompt **"Who are you?"**
- the program pauses and waits
- the user types something
- when the user presses Enter, Python stores that text in **"nam"**

Important point:

The value returned by **"input()"** is always a **string**.

Even if the user types:

"1234"

Python stores it as the string **"'1234'"**, not the number **1234**.

So if you want to use input as a number, you usually convert it with **"int()"** or **"float()"**.

## `print()` with commas

The **"print()"** function can display more than one thing at a time.

Example:

"print('Welcome', nam)"

When you separate values with commas in **"print()"**, Python automatically puts a space between them.

So if the user types:

"'Chuck'"

the output becomes:

"'Welcome Chuck'"

The space comes from the comma inside **"print()"**.

## What this lesson does

- explains that every value in Python has a **type**
- shows that Python keeps track of both **value** and **type**
- explains how the **"+"** operator behaves differently with integers and strings
- introduces **TypeError**
- explains how to read a **traceback**
- introduces the **"type()"** function
- explains the difference between **integers** and **floating-point numbers**
- introduces the **"int()"** and **"float()"** conversion functions
- explains that **input()** always returns a string
- shows how **print()** works with commas

## What I learn from this lesson

- that Python keeps track of the **type** of each value
- that the same operator can behave differently depending on type
- that **"+"** adds numbers but concatenates strings
- that Python gives a **traceback** when it cannot perform an operation
- how to use **"type()"** to inspect a value
- the difference between **int**, **float**, and **string**
- how to convert values with **"int()"** and **"float()"**
- that **input()** returns text as a string
- that values from the keyboard often need conversion before calculation

  ---

  # Lesson 4: Writing Comments in Python - First IPO Program

In this lesson, we combine many ideas from the previous lessons and write a complete Python program. Before building the program, we first learn about **comments** and why they are useful. Then we use the **IPO model**: **Input, Processing, Output**.

This is the first small Python program that really does something from beginning to end.

## Writing Comments in Python

A **comment** is text written in a Python program that is ignored by Python.

Comments are written with the **"#"** symbol.

Example:

"# this is a comment"

Python does not run comments. They are only there for humans reading the code.

## Why comments are useful

Comments help explain what the code is doing.

They are useful because:

- they help you remember your own code later
- they help explain more complex parts of a program
- they make code easier to read
- they can be used to temporarily disable a line of code

A very important idea in programming is that comments are often a gift to your **future self**.

When you come back to your code after a day, a week, or a month, comments can help you understand what you were trying to do.

## Good comments

A good comment explains something that is not immediately obvious.

For example, if a group of lines is doing one clear task, a comment can introduce that task.

Example:

"# get the name of the file and open it"

This helps the reader understand the purpose of the next lines.

## Bad comments

A bad comment says something obvious that everyone can already see.

Example:

"x = 1   # put 1 in x"

This comment is not useful because the line already clearly says that.

So comments should not repeat the code. They should explain the idea behind the code.

## Comments can disable code

Sometimes programmers use comments to temporarily turn off a line of code.

Example:

"# print('debug info')"

This is useful when testing or debugging a program, because the code is still there if you want to use it again later.

## Code with comments

Here is a simple example showing comments in a program:

"# get the name of the file and open it"

"# count the word frequency"

"# print the results"

These comments act like short explanations for different parts of the code.

## The IPO model

A common programming pattern is:

- **Input**
- **Processing**
- **Output**

This is often called the **IPO model**.

### Input
The program gets data from somewhere.

This could come from:

- the keyboard
- a file
- a database
- a web service

### Processing
The program works with the data.

This usually means:

- calculating something
- changing the data
- combining values
- solving a problem

### Output
The program shows the result.

This might be:

- printed on the screen
- written to a file
- sent somewhere else

This lesson introduces a very small program that uses all three parts.

## First IPO Program

The goal of this program is to convert a European elevator floor number into the equivalent United States floor number.

In many places in Europe:

- the ground floor is floor **0**

In the United States:

- the ground floor is floor **1**

So to convert a European floor to a United States floor, we add **1**.

## Code

"# convert elevator floors"

"inp = input('European floor? ')"

"usf = int(inp) + 1"

"print('US floor', usf)"

## Explanation

### "# convert elevator floors"

This is a comment.

It explains what the program is about.

Python ignores this line.

### "inp = input('European floor? ')"

This is the **input** part.

Python prints:

"'European floor? '"

Then it waits for the user to type something.

If the user types:

"'0'"

then that value is stored in **"inp"**.

Important: the result of **"input()"** is always a **string**.

So **"inp"** contains the string **"'0'"**, not the integer **0**.

### "usf = int(inp) + 1"

This is the **processing** part.

First, Python converts **"inp"** from a string to an integer using **"int()"**.

The name **"usf"** is a mnemonic variable name meaning **United States floor**.

### "print('US floor', usf)"

This is the **output** part.

The comma in **"print()"** automatically adds a space between the text and the number.


## Why this program is important

This program is simple, but it uses many ideas learned so far:

- comments
- variables
- input
- type conversion
- arithmetic
- output
- mnemonic variable names

It is the first full Python program with a beginning, a middle, and an end.

## What this lesson does

- explains how to write **comments** in Python
- shows why comments are useful for humans
- explains the **IPO model**
- introduces the first complete Python program
- shows how to get input from the user
- shows how to process the input with **"int()"** and **"+ 1"**
- shows how to print the result

## What I learn from this lesson

- that comments begin with **"#"**
- that comments are ignored by Python
- that comments help explain code for humans
- that useful comments explain ideas, not obvious lines
- that many programs follow the **Input, Processing, Output** pattern
- how to read input with **"input()"**
- how to convert input from string to integer with **"int()"**
- how to print results with **"print()"**
- how to write my first small complete Python program
