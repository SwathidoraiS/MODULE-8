# # 🔢 Hackerrank:# 🏆 Student Topper Finder

This Python program helps determine the **top-performing student** based on the total marks across five subjects. It uses a dictionary to store each student’s marks and identifies the topper using simple calculations and built-in functions.

---

## 🎯 Aim

To maintain a dictionary of students with their marks in five subjects, calculate their **total marks**, store them in a new dictionary, and identify the **student with the highest total (topper)**.

---

## 🧠 Algorithm

1. **Start** the program.
2. Create a dictionary `student_marks`:
   - Keys → Student names.
   - Values → List of marks in five subjects.
3. Initialize an empty dictionary `total_marks`.
4. Loop through `student_marks`:
   - Calculate the total marks using `sum()`.
   - Store the result in `total_marks`.
5. Use `max()` on `total_marks` to find the student with the highest total.
6. Print:
   - The `total_marks` dictionary.
   - The **topper's name and score**.

---

## 💻 PROGRAM:
```
students = {
    "Alice": [85, 90, 78, 92, 88],
    "Bob": [75, 80, 70, 85, 78],
    "Charlie": [90, 95, 88, 92, 91],
    "David": [60, 65, 70, 55, 62]
}

total_marks = {}

for student, marks in students.items():
    total_marks[student] = sum(marks)

print("Total Marks for each student:")
for student, total in total_marks.items():
    print(f"{student}: {total}")

topper = max(total_marks, key=total_marks.get)
topper_marks = total_marks[topper]

print(f"\nThe student with the highest total marks is {topper} with {topper_marks} marks.")
```
## OUTPUT:
```
Input                                         Result
Alice [85, 90, 78, 92, 88]              
Bob [75, 80, 70, 85, 78]                   The student with the highest total marks is Charlie with 456 marks.
Charlie [90, 95, 88, 92, 91]
David [60, 65, 70, 55, 62]
```
## RESULT:
The program was successful.

# 🔄 Hackerrank : # 📦 Python Word Wrap Function

This Python program defines a function that **wraps a long string into multiple lines**, ensuring each line does not exceed a specified width.

---

## 🎯 Aim

To write a Python function that takes a long string and a specified width, and returns the string formatted with line breaks such that each line has **at most the given width**.

---

## 🧠 Algorithm

1. **Start** the program.
2. Define a function `wrap(string, max_width)`:
   - Create an empty list `wrapped_lines` to store parts of the string.
   - Loop through the string using steps of `max_width`.
   - In each iteration, extract a substring of length `max_width`.
   - Append this substring to the list.
3. Join the list with `\n` to create the final string.
4. Return the result.
5. **End** the program.

---


## 🧪 Program
```
def format_string(input_string, width):

    words = input_string.split()
    
    # Initialize an empty list to store the formatted lines
    lines = []
    current_line = ""
    for word in words:
        # If adding the next word exceeds the width, start a new line
        if len(current_line) + len(word) + 1 > width:
            lines.append(current_line)
            current_line = word
        else:
  
            if current_line:
                current_line += " " + word
            else:
                current_line = word
    if current_line:
        lines.append(current_line)
   
    return "\n".join(lines)

input_string = "This is an example of a long string that will be formatted into multiple lines based on the specified width."
width = 20
formatted_string = format_string(input_string, width)
print(formatted_string)
```
## Output:
```
This is an example
of a long string
that will be
formatted into
multiple lines based
on the specified
width.
```
## Result:
The program was successful.

# 🎓 Hackerrank:Python Program to Find Students with the Second Lowest Grade

This program reads student names and their corresponding grades, identifies the **second lowest grade**, and prints the names of all students who have that grade in **alphabetical order**.

---

## 🎯 Aim

To write a Python program to:
- Read a list of students and their grades.
- Identify the second lowest grade.
- Print the names of students who have that grade, sorted alphabetically.

---

## 🧠 Algorithm

1. **Read** an integer `n` representing the number of students.
2. **Read** each student’s name and grade, and store them as a sublist inside a list.
3. **Extract** all the grades and sort them.
4. **Identify** the second lowest grade from the sorted grade list.
5. **Collect** names of all students whose grade matches the second lowest grade.
6. **Sort** the names alphabetically.
7. **Print** each name on a new line.

---

## 💻  Program
```
students = [
    ("Alice", 85),
    ("Bob", 75),
    ("Charlie", 90),
    ("David", 75),
    ("Eva", 80),
    ("Frank", 85)
]
grades = [grade for name, grade in students]
unique_grades = sorted(set(grades))  # Remove duplicates and sort the grades
second_lowest_grade = unique_grades[1]  
students_with_second_lowest = [name for name, grade in students if grade == second_lowest_grade]
students_with_second_lowest.sort()
print("Students with the second lowest grade:")
for student in students_with_second_lowest:
    print(student)

```
## Output:
```
Input                                Result
 [("Alice", 85),
    ("Bob", 75),
    ("Charlie", 90),              [("Alice", 85), ("Bob", 75), ("Charlie", 90), ("David", 75), ("Eva", 80), ("Frank", 85)]
    ("David", 75),
    ("Eva", 80),
    ("Frank", 85)]
```
## Result:
The program was successful.

# 🏆 Hackerrank:Runner-Up Score Finder in Python

## 🎯 AIM:
To write a Python program that takes a list of scores from participants and finds the **runner-up score** (i.e., the second-highest score), eliminating any duplicates.

---

## 🧠 ALGORITHM:

1. **Start**
2. Create a variable `n` and get its value from the user (number of participants)
3. Read the list of `n` scores from the user using `input().split()` and convert them to integers
4. Store the scores in a list
5. Use `set()` to remove any duplicate scores
6. Convert the set back to a list and sort it in ascending order
7. Print the second-last element of the sorted list (i.e., the runner-up score)
8. **Stop**

---

## 💻 PROGRAM:
```
def find_runner_up(scores):
   
    unique_scores = set(scores)
    sorted_scores = sorted(unique_scores, reverse=True)

    if len(sorted_scores) > 1:
        return sorted_scores[1]
    else:
        return None  # Return None if there is no runner-up

scores = [45, 67, 89, 89, 91, 67, 72, 91]

runner_up = find_runner_up(scores)

if runner_up is not None:
    print(f"The runner-up score is: {runner_up}")
else:
    print("There is no runner-up score.")
```
## OUTPUT:
```
           Input                                              Result
 [45, 67, 89, 89, 91, 67, 72, 91]                [45, 67, 89, 89, 91, 67, 72, 91]
````
## RESULT:
The program was successful.

# 🔍 Hackerrank:Python Program to Check if a String Ends with a Numeric Digit

This Python program checks whether the last character of a given input string is a **numeric digit (0–9)**.

---

## 🎯 Aim

To write a Python program that checks if a given string ends with a number using Python's built-in string methods.

---

## 🧠 Algorithm

1. **Start the program.**
2. **Input** a string from the user.
3. **Access** the last character using indexing (`string[-1]`).
4. **Check** if the last character is a digit using the `.isdigit()` method.
5. **If true**, print that the string ends with a number.
6. **Else**, print that the string does not end with a number.
7. **End the program.**

---

## 💻  Program
```
def ends_with_number(s):
    return s[-1].isdigit() if s else False
input_string = "Hello123"
if ends_with_number(input_string):
    print(f"The string '{input_string}' ends with a number.")
else:
    print(f"The string '{input_string}' does not end with a number.")
```
## Output:
```
   Input                            Result

 'Hello123'                  The string 'Hello123' ends with a number.
```
## Result:
The program was successful.
