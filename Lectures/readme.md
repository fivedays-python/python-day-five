### **Lecture Notes**

#### **1. Advanced Data Structures**

##### **List Comprehensions**

Concise way to create lists.

**Syntax:**

```python
new_list = [expression for item in iterable if condition]
```

**Example:**

```python
squares = [x**2 for x in range(1, 11)]
print(squares)
```

**Output:**

```
[1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
```

##### **Dictionary Comprehensions**

**Example:**

```python
square_dict = {x: x**2 for x in range(1, 6)}
print(square_dict)
```

**Output:**

```
{1: 1, 2: 4, 3: 9, 4: 16, 5: 25}
```

##### **Generators**

Functions that return an iterator.

**Example:**

```python
def generate_numbers(n):
    for i in range(n):
        yield i

gen = generate_numbers(5)
for num in gen:
    print(num)
```

**Output:**

```
0
1
2
3
4
```

---

#### **2. Working with External Libraries**

##### **NumPy**

Numerical Python library for array computations.

**Example:**

```python
import numpy as np

arr = np.array([1, 2, 3, 4, 5])
print(arr * 2)
```

**Output:**

```
[ 2  4  6  8 10]
```

##### **pandas**

Data manipulation and analysis library.

**Example:**

```python
import pandas as pd

data = {'Name': ['Alice', 'Bob', 'Charlie'], 'Age': [25, 30, 35]}
df = pd.DataFrame(data)
print(df)
```

**Output:**

```
      Name  Age
0    Alice   25
1      Bob   30
2  Charlie   35
```

---

#### **3. Regular Expressions**

Used for pattern matching in strings.

**Import the `re` Module:**

```python
import re
```

##### **Common Functions:**

- **`re.match()`**: Checks for a match at the beginning of a string.
- **`re.search()`**: Searches the string for a match anywhere.
- **`re.findall()`**: Returns a list of all matches.

**Example:**

```python
pattern = r'\d+'  # Matches one or more digits
text = "There are 12 apples and 24 bananas."

numbers = re.findall(pattern, text)
print(numbers)
```

**Output:**

```
['12', '24']
```
