### **4. Hands-On Exercise**

#### **Exercise:** Student Grades Calculator

**Objective:** Create a program that reads student names and grades from a CSV file, calculates the average grade, and writes the results to a new CSV file.

**Instructions:**

1. **Create the Input CSV File (`students.csv`):**

   ```
   Name,Grade
   Alice,85
   Bob,78
   Charlie,92
   Diana,88
   Edward,76
   ```

2. **Write a Program (`grades_calculator.py`) That:**

   - Reads the student names and grades from `students.csv`.
   - Calculates the average grade.
   - Writes each student's name and grade to a new CSV file `results.csv`.
   - Appends the class average at the end of `results.csv`.

3. **Use Modules and Functions:**

   - Use the `csv` module for file operations.
   - Organize your code using functions.

#### **Solution:**

```python
# grades_calculator.py

import csv

def read_grades(filename):
    grades = []
    students = []
    with open(filename, 'r') as csvfile:
        reader = csv.DictReader(csvfile)
        for row in reader:
            students.append(row['Name'])
            grades.append(float(row['Grade']))
    return students, grades

def calculate_average(grades):
    total = sum(grades)
    count = len(grades)
    average = total / count
    return average

def write_results(filename, students, grades, average):
    with open(filename, 'w', newline='') as csvfile:
        fieldnames = ['Name', 'Grade']
        writer = csv.DictWriter(csvfile, fieldnames=fieldnames)

        writer.writeheader()
        for name, grade in zip(students, grades):
            writer.writerow({'Name': name, 'Grade': grade})

        writer.writerow({'Name': 'Average', 'Grade': average})

def main():
    input_file = 'students.csv'
    output_file = 'results.csv'

    students, grades = read_grades(input_file)
    average = calculate_average(grades)
    write_results(output_file, students, grades, average)

    print(f"Processed {len(students)} students.")
    print(f"Class average: {average:.2f}")
    print(f"Results written to {output_file}")

if __name__ == "__main__":
    main()
```

#### **Explanation:**

- **`read_grades()` Function:**
  - Reads student names and grades from the input CSV file.
  - Returns two lists: `students` and `grades`.

- **`calculate_average()` Function:**
  - Calculates the average of the grades.

- **`write_results()` Function:**
  - Writes the students' names and grades to the output CSV file.
  - Appends the class average at the end.

- **`main()` Function:**
  - Coordinates the reading, processing, and writing of data.

#### **Running the Program:**

1. Ensure `students.csv` is in the same directory as `grades_calculator.py`.
2. Run the script:

   ```bash
   python grades_calculator.py
   ```

3. Check the `results.csv` file for the output.

**Sample `results.csv`:**

```
Name,Grade
Alice,85.0
Bob,78.0
Charlie,92.0
Diana,88.0
Edward,76.0
Average,83.8
```

---
