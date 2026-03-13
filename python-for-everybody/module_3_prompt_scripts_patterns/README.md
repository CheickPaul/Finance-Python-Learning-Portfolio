# First Python Script and Basic Instructions in Python

This lesson explains how Python starts, how to give it instructions, how variables work, and why writing code in a script file is better than typing too much in interactive mode.

## Code

"x = 1"

"print(x)"

"x = x + 1"

"print(x)"

## Explanation

### "x = 1"
This line creates a variable called **"x"** and stores the value **1** in it.

- **"x"** is the variable name
- **"="** is used for assignment
- **"1"** is the value stored in memory

In programming, this does not mean the same thing as in math.  
It means: put the value **1** into the variable **"x"**.

### "print(x)"
This line prints the value stored in **"x"**.

- **"print()"** is used to display something on the screen
- Python looks inside **"x"**
- then it shows the value

At this moment, Python prints:

"1"

### "x = x + 1"
This line takes the current value of **"x"**, adds **1**, and stores the result back into **"x"**.

Step by step:

- Python reads the value in **"x"**
- adds **1**
- stores the new result in **"x"**

So if **"x"** was **1**, it becomes **2**.

### "print(x)"
This prints the new value of **"x"**.

Now Python prints:

"2"

## Reserved Words

Python has special words called **reserved words**.

These words already have a meaning in Python, so we cannot use them as variable names.

Examples of reserved words:

- **"for"**
- **"while"**
- **"if"**
- **"import"**
- **"return"**

These words must be used only the way Python expects.

## Interactive Mode

Python can run in **interactive mode**.

This means you type instructions directly, one line at a time, and Python answers immediately.

Example:

"x = 1"  
"print(x)"

This is useful for small tests.

## Script Files

When the code becomes longer, it is better to write it in a file.

A Python script is a text file that contains Python instructions.

Python files usually end with:

".py"

Example:

"hello.py"

A script is easier to:

- save
- read again
- correct
- run many times

## What this lesson shows

- how to start giving instructions to Python
- how to store a value in a variable
- how to display a value with **"print()"**
- how to update a variable with **"x = x + 1"**
- what reserved words are
- the difference between interactive mode and a Python script

## Example

This code:

"x = 1"  
"print(x)"  
"x = x + 1"  
"print(x)"

Produces:

"1"  
"2"

## What I learn from this lesson

- how Python executes instructions line by line
- how to create and use a variable
- how assignment works in Python
- how to display values with **"print()"**
- how to increase a variable by **1**
- why reserved words are important
- why using a **.py** script is useful
