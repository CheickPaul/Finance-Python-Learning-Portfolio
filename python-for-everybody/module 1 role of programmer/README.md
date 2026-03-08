# Module 1 - Role of the Programmer (Personal Notes)

## Why We Program 

- In this video, I understood that the goal of the course is to help me go from a **technology user** to a **technology creator**.
- A computer is not really “smart” by itself. It only follows **instructions step by step**. When it is on, it is like it is waiting for the next instruction.
- The job of a programmer is to be a link between the **user** (what they want) and the **hardware/computer** (what can do the work).
- I also learned that programming is useful even if I don’t want to be a professional developer. I can write small programs for myself, for example to work with data or to automate a task.
- Big difference: humans can ignore or fix small mistakes, but computers usually **cannot**. A small mistake can stop the program with a **syntax error**.
- The example about counting words was important: it is boring for people, but computers are very good at it. With a few lines of Python, I can make the computer do this work for me.


## Hardware Architecture 

- In this video, I learned the basic computer “block diagram” so I can understand the main terms used in the course: **CPU**, **main memory**, **secondary memory**, and **input/output devices**.

- **The 4 components to remember are:**
  - **Input/Output devices (I/O)**: keyboard, mouse, screen, etc.
  - **CPU (Central Processing Unit)**: executes instructions and performs arithmetic + logical operations (it keeps asking “what next?”).
  - **Main Memory (RAM)**: fast temporary memory that **stores the data and instructions actively being used by the CPU** (RAM does not execute instructions).
  - **Secondary Memory (Storage)**: permanent memory (hard drive / SSD / USB) where files are saved.

- When I write a Python program, I first save it as a file in **secondary memory** (example: `program.py`). Then, when I run it, the program is loaded into **main memory (RAM)**.
- Main memory is **fast but temporary**: when the computer turns off, the data in RAM disappears. Secondary memory is **permanent**: files stay there even when the power is off.

- The CPU follows a repeating process called the **fetch–decode–execute cycle**:
  - **Fetch**: retrieve the next instruction from **main memory (RAM)**
  - **Decode**: understand what the instruction means
  - **Execute**: perform the instruction

- The CPU ultimately understands only **machine language** (zeros and ones). Python code must be translated into machine language by an **interpreter** (or sometimes a compiler). For now, I focus on writing Python.

- Programming is **a sequence of instructions executed by a computer**.
- A common beginner challenge in Python is **indentation**, because it is part of Python syntax and defines code blocks.
- **CPU executes**, **RAM stores (temporary)**, **Storage saves files (permanent)**, and **Fetch** is the step that retrieves instructions from memory.

## Python as a Language 

- In this course, we learned why Python is a great first programming language: it is designed to be **easy to learn**, **fun**, but also **powerful** and useful.
- Even though Python uses a snake theme, it was not named after a snake. Python was named after **Monty Python’s Flying Circus**, because Guido van Rossum wanted the language to feel playful and enjoyable.
- Guido created Python to avoid the style of older languages that were very serious and complex. The goal was to make a language that is both **simple** and **strong**.
- As we learn Python, we should expect to make many mistakes. The computer will often show **syntax error**.
- A **syntax error** is not a judgement about us. It simply means Python is **lost** and does not understand our code.
- We are learning Python’s language because Python cannot learn ours. We need to be patient, practice, and trust the process.
- At the beginning, learning programming can feel confusing and frustrating, but with time the basics connect and it starts to make sense.
