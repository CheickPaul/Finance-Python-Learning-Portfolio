# L1 : First Python Script and Basic Instructions in Python

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
  
---

# L2: Writing Paragraphs of Code in Python

This lesson explains how Python programs are built using basic programming patterns such as sequence, conditionals, loops, and storing values. These patterns are combined to create longer and more useful programs.

## Code

"x = 2"

"print(x)"

"x = x + 2"

"print(x)"

"x = 15"

"if x < 10:"
"    print('smaller')"

"if 10 <= x <= 20:"
"    print('average')"

"if x > 20:"
"    print('bigger')"

"print('done')"

"n = 5"

"while n > 0:"
"    print(n)"
"    n = n - 1"

"print('Blastoff!')"

## Explanation

### "x = 2"
This line creates a variable called **"x"** and stores the value **2** in it.

- **"x"** is the variable name
- **"="** is the assignment operator
- **"2"** is the value stored in memory

This means: put the value **2** into the variable **"x"**.

### "print(x)"
This line prints the current value of **"x"**.

- **"print()"** is a function
- it displays the value on the screen
- Python reads the value inside **"x"** and shows it

At this moment, Python prints:

"2"

### "x = x + 2"
This line takes the current value of **"x"**, adds **2**, and stores the new result back into **"x"**.

Step by step:

- Python reads the current value of **"x"**
- adds **2**
- stores the result back into **"x"**

If **"x"** was **2**, it becomes **4**.

### "print(x)"
This line prints the new value of **"x"**.

Python prints:

"4"

### "x = 15"
This line creates a variable called **"x"** and stores the value **15** in it.

This new value is used for the conditional examples below.

### "if x < 10:"
This line starts a conditional statement.

Python asks this question:

Is **"x"** less than **10**?

- if the answer is **True**, Python runs the indented line below
- if the answer is **False**, Python skips it

Since **"x"** is **15**, the condition is false.

### "    print('smaller')"
This line does not run, because the condition **"x < 10"** is false.

Python skips this line.

### "if 10 <= x <= 20:"
This line starts another conditional statement.

Python asks this question:

Is **"x"** between **10** and **20**?

- if the answer is **True**, Python runs the indented line below
- if the answer is **False**, Python skips it

Since **"x"** is **15**, the condition is true.

### "    print('average')"
This line runs because the condition **"10 <= x <= 20"** is true.

Python prints:

"average"

### "if x > 20:"
This line starts another conditional statement.

Python asks this question:

Is **"x"** greater than **20**?

- if the answer is **True**, Python runs the indented line below
- if the answer is **False**, Python skips it

Since **"x"** is **15**, the condition is false.

### "    print('bigger')"
This line does not run, because the condition **"x > 20"** is false.

Python skips this line.

### "print('done')"
This line is outside the **if** blocks, so Python runs it no matter what.

Python prints:

"done"

### "n = 5"
This line creates a variable called **"n"** and stores the value **5** in it.

- **"n"** is the variable name
- **"="** is the assignment operator
- **"5"** is the starting value

This variable is used to control the loop.

### "while n > 0:"
This line starts a **while loop**.

Python asks this question:

Is **"n"** greater than **0**?

- if the answer is **True**, Python runs the indented lines below
- if the answer is **False**, Python stops the loop

This means the loop will continue as long as **"n"** is greater than **0**.

### "    print(n)"
This line prints the current value of **"n"**.

At each loop, Python shows the value before changing it.

So Python prints:

"5"  
"4"  
"3"  
"2"  
"1"

### "    n = n - 1"
This line decreases the value of **"n"** by **1**.

Step by step:

- Python reads the current value of **"n"**
- subtracts **1**
- stores the new value back into **"n"**

This is very important because it changes the loop variable and helps the loop stop.

If this line did not exist, the loop could continue forever.

### "print('Blastoff!')"
This line runs after the loop finishes.

When **"n"** becomes **0**, the condition **"n > 0"** becomes false, so Python exits the loop.

Then Python prints:

"Blastoff!"

## Sequence Pattern

A sequence means Python runs instructions **one after another**, in order.

Example:

"x = 2"  
"print(x)"  
"x = x + 2"  
"print(x)"

Python starts at the first line, then moves to the next, and continues until the program ends.

This is the simplest programming pattern.

## Conditional Pattern

A conditional lets Python make a decision.

Example:

"x = 15"

"if x < 10:"
"    print('smaller')"

"if 10 <= x <= 20:"
"    print('average')"

"if x > 20:"
"    print('bigger')"

"print('done')"

Python checks each condition and decides whether to run or skip the indented code.

## Loop Pattern

A loop tells Python to repeat a set of instructions.

Example:

"n = 5"

"while n > 0:"
"    print(n)"
"    n = n - 1"

"print('Blastoff!')"

Python repeats the indented block until the condition becomes false.

## Indentation

Python uses **indentation** to show which lines belong to a block of code.

Examples:

- the indented line after **"if"** belongs to the conditional block
- the indented lines after **"while"** belong to the loop block

Indentation is very important in Python.

## Infinite Loops

A loop can become an **infinite loop** if the condition never becomes false.

Example:

"while n > 0:"
"    print(n)"

This would repeat forever if **"n"** never changes.

That is why loops often use a variable that changes each time through the loop.

## Nesting

Sometimes one structure is placed inside another structure.

For example:

- an **if** inside a **for**
- a **for** inside another **for**

This is called **nesting**.

Python uses nesting to build more complex programs.

## Paragraphs of Code

A longer Python program is built like a story:

- words become instructions
- instructions become lines
- lines become paragraphs
- paragraphs become a complete program

A program often contains:

- sequential code
- repeated code
- conditional code

These patterns work together to solve a problem.

## What this lesson shows

- how Python programs are built from simple patterns
- how sequence executes instructions in order
- how conditionals allow Python to make decisions
- how loops repeat instructions
- why indentation matters in Python
- how loops stop when a condition becomes false
- what an infinite loop is
- how different code structures can be combined

## Example

This code:

"x = 15"  
"if x < 10:"  
"    print('smaller')"  
"if 10 <= x <= 20:"  
"    print('average')"  
"if x > 20:"  
"    print('bigger')"  
"print('done')"

Produces:

"average"  
"done"

This code:

"n = 5"  
"while n > 0:"  
"    print(n)"  
"    n = n - 1"  
"print('Blastoff!')"

Produces:

"5"  
"4"  
"3"  
"2"  
"1"  
"Blastoff!"

## What I learn from this lesson

- how to write code in sequence
- how to use **if** for decisions
- how to test multiple conditions
- how to display **"average"** when a value is between **10** and **20**
- how to use **while** to repeat instructions
- why indentation is important in Python
- how loops work step by step
- how to avoid infinite loops
- how programs are built by combining simple patterns
