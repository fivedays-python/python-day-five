## **Lecture Notes**

### **1. Review of Key Concepts**

Before diving into new topics, let's briefly revisit some essential Python concepts.

#### **Variables and Data Types**

- **Variables:** Store data values.
- **Data Types:** Integers, floats, strings, booleans, lists, tuples, dictionaries.

**Example:**

```python
name = "Alice"
age = 25
grades = [85, 90, 78]
```

#### **Control Structures**

- **Conditional Statements:** `if`, `elif`, `else`.
- **Loops:** `for`, `while`.

**Example:**

```python
if age >= 18:
    print("You are an adult.")
else:
    print("You are a minor.")
```

#### **Functions**

- Reusable blocks of code defined using `def`.

**Example:**

```python
def greet(name):
    return f"Hello, {name}!"

print(greet("Alice"))
```

#### **Data Collections**

- **Lists:** Ordered, mutable collections.
- **Dictionaries:** Unordered collections of key-value pairs.

---

### **2. Modules and Packages**

Modules and packages help organize your code and reuse functionality across different programs.

#### **What is a Module?**

- A **module** is a file containing Python definitions and statements.
- Modules allow you to organize code into separate files for better manageability.

#### **Importing Standard Library Modules**

Python comes with a rich set of modules known as the **standard library**.

**Commonly Used Modules:**

- `math`: Mathematical functions.
- `random`: Generating random numbers.
- `datetime`: Working with dates and times.
- `os`: Interacting with the operating system.

**Example:**

```python
import math

print(math.sqrt(16))  # Outputs: 4.0
```

#### **Using Functions from Modules**

Access functions and variables using the dot `.` notation.

**Example:**

```python
import random

number = random.randint(1, 10)
print(f"Random number between 1 and 10: {number}")
```

#### **Creating Your Own Modules**

1. **Create a Python File (Module):**

   - Create a new file named `utilities.py`.

   ```python
   # utilities.py

   def add(a, b):
       return a + b

   def subtract(a, b):
       return a - b
   ```

2. **Import and Use Your Module:**

   - In your main script `main.py`, import your custom module.

   ```python
   # main.py

   import utilities

   result = utilities.add(5, 3)
   print(f"Addition Result: {result}")
   ```

**Note:** Make sure both files are in the same directory.

#### **Benefits of Using Modules**

- **Code Reusability:** Write code once and use it in multiple programs.
- **Organization:** Keep your codebase organized and manageable.
- **Namespace Management:** Avoid naming conflicts by encapsulating code within modules.

---

### **3. Working with External Data**

Handling data from external files is a common task in programming.

#### **Reading from a CSV File**

A **CSV (Comma-Separated Values)** file stores tabular data in plain text.

**Example CSV (`students.csv`):**

```
Name,Grade
Alice,85
Bob,78
Charlie,92
```

**Reading a CSV File:**

```python
import csv

with open('students.csv', 'r') as csvfile:
    reader = csv.reader(csvfile)
    for row in reader:
        print(row)
```

**Output:**

```
['Name', 'Grade']
['Alice', '85']
['Bob', '78']
['Charlie', '92']
```

#### **Writing to a CSV File**

**Writing Data to a CSV File:**

```python
import csv

data = [
    ['Name', 'Grade'],
    ['Alice', '85'],
    ['Bob', '78'],
    ['Charlie', '92']
]

with open('output.csv', 'w', newline='') as csvfile:
    writer = csv.writer(csvfile)
    writer.writerows(data)
```

#### **Calculating Averages**

Let's write a function to calculate the average grade.

```python
def calculate_average(grades):
    total = sum(grades)
    count = len(grades)
    average = total / count
    return average
```

---
