### Practice: Writing and Running a Python Script with VS Code and CMD

In this exercise, I learned how to write and run a Python program on Windows using **VS Code** and **CMD**.

I used **VS Code** to write my Python code in a file, then I saved that file as **`programme.py`**. After that, I opened **CMD** to run the file from the terminal.

#### Code used

`print("I am learning to code in Python")`

#### Method used

In **VS Code**:
- write the code
- save the file as **`programme.py`**

In **CMD**:
1. go to the Desktop with **`cd Desktop`**
2. display the contents of the Desktop with **`dir`**
3. enter the **python** folder with **`cd python`**
4. check that the file is there with **`dir`**
5. run the program with **`python programme.py`**

#### Important commands

**`cd`**  
The command `cd` means **change directory**. It is used to move from one folder to another.

Examples:
- `cd Desktop`
- `cd python`

**`dir`**  
The command `dir` is used to display the contents of the current folder.

Example:
- `dir`

**`python programme.py`**  
This command is used to run the Python file.

Example:
- `python programme.py`

#### Commands used

`cd Desktop`  
`dir`  
`cd python`  
`dir`  
`python programme.py`

#### Result

The program displays:

`I am learning to code in Python`

#### What I learned

- write a program in VS Code
- save a Python file with the **`.py`** extension
- use CMD to move through folders
- use **`cd`** to change folders
- use **`dir`** to see files
- run a Python script with **`python programme.py`**

  ---

  # Reading a Text File Line by Line in Python

This Python program opens a text file, reads it line by line, prints each line, and counts how many lines the file contains.

## Code

"fh = open('romeo.txt', 'r')"

"count = 0"

"for line in fh:"
"    print(line.strip())"
"    count = count + 1"

"print(count, 'Lines')"

## Explanation

### "fh = open('romeo.txt', 'r')"
This line opens the file named **'romeo.txt'** in read mode.

- **"open(...)"** is used to open a file
- **"'romeo.txt'"** is the file name
- **"'r'"** means **read**
- **"fh"** stands for **file handle**, which is a variable used to work with the opened file

### "count = 0"
This creates a variable called **"count"** and sets it to **0**.

Its role is to count how many lines are in the file.

### "for line in fh:"
This loop reads the file **one line at a time**.

At each iteration, the variable **"line"** contains one line from the file.

### "print(line.strip())"
This prints the current line.

- **"strip()"** removes extra spaces and the newline character at the beginning and end of the line
- this avoids blank lines when printing

### "count = count + 1"
Each time a line is read, the counter increases by **1**.

### "print(count, 'Lines')"
At the end, the program prints the total number of lines in the file.

## What this program does

- opens a text file
- reads the file line by line
- prints each line
- counts the number of lines
- displays the total at the end

## Example

If **'romeo.txt'** contains:

"But soft what light"  
"through yonder window breaks"  
"It is the east"  
"and Juliet is the sun"

The output will be:

"But soft what light"  
"through yonder window breaks"  
"It is the east"  
"and Juliet is the sun"  
"4 Lines"

## What I learn from this program

- how to open a file in Python
- how to read a file line by line
- how to use a **"for"** loop with a file
- how to count lines with a variable
- how to clean line output with **"strip()"**
