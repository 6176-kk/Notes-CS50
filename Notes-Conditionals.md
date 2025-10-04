# CS50 Python - Lesson 2: Conditionals

## 📚 Table of Contents
- [Introduction](#introduction)
- [Comparison Operators](#comparison-operators)
- [If Statements](#if-statements)
- [If-Else Statements](#if-else-statements)
- [If-Elif-Else Statements](#if-elif-else-statements)
- [Logical Operators](#logical-operators)
- [Modulo Operator](#modulo-operator)
- [Boolean Values](#boolean-values)
- [Pythonic Conditionals](#pythonic-conditionals)
- [Match Statements](#match-statements)
- [Practice Exercises](#practice-exercises)

---

## Introduction

**Conditionals** allow your program to make decisions and execute different code based on different conditions. They're like forks in the road—your program chooses which path to take.

### Real-World Examples
- 🌡️ If temperature > 30°C, turn on AC
- 🔐 If password is correct, log in
- 💰 If balance < 0, charge overdraft fee
- 🎮 If score > high_score, save new record

---

## Comparison Operators

**Comparison operators** compare two values and return `True` or `False`.

| Operator | Meaning | Example | Result |
|----------|---------|---------|--------|
| `>` | Greater than | `5 > 3` | `True` |
| `<` | Less than | `5 < 3` | `False` |
| `>=` | Greater than or equal | `5 >= 5` | `True` |
| `<=` | Less than or equal | `3 <= 5` | `True` |
| `==` | Equal to | `5 == 5` | `True` |
| `!=` | Not equal to | `5 != 3` | `True` |

### Examples

```python
x = 10
y = 5

print(x > y)   # True
print(x < y)   # False
print(x == 10) # True
print(x != y)  # True
```

⚠️ **Common Mistake:**
```python
# ❌ Wrong - assignment, not comparison
if x = 10:

# ✅ Correct - comparison
if x == 10:
```

---

## If Statements

The **if statement** executes code only when a condition is `True`.

### Basic Syntax

```python
if condition:
    # Code here runs only if condition is True
    # Notice the indentation (4 spaces or 1 tab)
```

### Example 1: Simple If

```python
x = int(input("What's x? "))

if x > 0:
    print("x is positive")
```

**Flow:**
- If user enters `5`: prints "x is positive"
- If user enters `-3`: prints nothing

### Example 2: Multiple If Statements

```python
x = int(input("What's x? "))

if x > 0:
    print("x is positive")

if x < 0:
    print("x is negative")

if x == 0:
    print("x is zero")
```

⚠️ **Issue:** This checks all three conditions even if the first one is true!

---

## If-Else Statements

The **else** clause runs when the if condition is `False`.

### Basic Syntax

```python
if condition:
    # Runs if condition is True
else:
    # Runs if condition is False
```

### Example 1: Even or Odd

```python
x = int(input("What's x? "))

if x % 2 == 0:
    print("Even")
else:
    print("Odd")
```

### Example 2: Grade Pass/Fail

```python
score = int(input("Score: "))

if score >= 60:
    print("Pass")
else:
    print("Fail")
```

---

## If-Elif-Else Statements

**elif** (else if) allows you to check multiple conditions in sequence.

### Basic Syntax

```python
if condition1:
    # Runs if condition1 is True
elif condition2:
    # Runs if condition1 is False and condition2 is True
elif condition3:
    # Runs if condition1 and condition2 are False and condition3 is True
else:
    # Runs if all conditions are False
```

### Example 1: Number Classification

```python
x = int(input("What's x? "))

if x > 0:
    print("x is positive")
elif x < 0:
    print("x is negative")
else:
    print("x is zero")
```

**Key Point:** Only ONE block executes. Once a condition is `True`, the rest are skipped!

### Example 2: Letter Grades

```python
score = int(input("Score: "))

if score >= 90:
    print("Grade: A")
elif score >= 80:
    print("Grade: B")
elif score >= 70:
    print("Grade: C")
elif score >= 60:
    print("Grade: D")
else:
    print("Grade: F")
```

### Example 3: Expanded Grades

```python
score = int(input("Score: "))

if score >= 90:
    print("Grade: A")
elif score >= 80:
    print("Grade: B")
elif score >= 70:
    print("Grade: C")
elif score >= 60:
    print("Grade: D")
else:
    print("Grade: F")

# Additional feedback
if score >= 60:
    print("You passed!")
else:
    print("You failed.")
```

---

## Logical Operators

**Logical operators** combine multiple conditions.

| Operator | Meaning | Example |
|----------|---------|---------|
| `and` | Both must be True | `x > 0 and x < 10` |
| `or` | At least one must be True | `x == 0 or x == 1` |
| `not` | Negates the condition | `not x > 0` |

### The `and` Operator

Both conditions must be `True`:

```python
age = int(input("Age: "))
has_license = input("Have license? (yes/no): ")

if age >= 16 and has_license == "yes":
    print("You can drive!")
else:
    print("You cannot drive.")
```

**Truth Table for `and`:**
| Condition 1 | Condition 2 | Result |
|-------------|-------------|--------|
| True | True | True ✅ |
| True | False | False |
| False | True | False |
| False | False | False |

### The `or` Operator

At least one condition must be `True`:

```python
day = input("What day is it? ")

if day == "Saturday" or day == "Sunday":
    print("It's the weekend!")
else:
    print("It's a weekday.")
```

**Truth Table for `or`:**
| Condition 1 | Condition 2 | Result |
|-------------|-------------|--------|
| True | True | True ✅ |
| True | False | True ✅ |
| False | True | True ✅ |
| False | False | False |

### The `not` Operator

Negates (reverses) a condition:

```python
is_raining = False

if not is_raining:
    print("You don't need an umbrella!")
```

### Combining Logical Operators

```python
age = int(input("Age: "))
day = input("Day: ")

if (age >= 13 and age <= 19) and (day == "Saturday" or day == "Sunday"):
    print("Teen weekend discount applies!")
```

---

## Modulo Operator

The **modulo operator** (`%`) returns the remainder of division.

```python
print(10 % 3)  # 1 (10 ÷ 3 = 3 remainder 1)
print(15 % 4)  # 3 (15 ÷ 4 = 3 remainder 3)
print(8 % 2)   # 0 (8 ÷ 2 = 4 remainder 0)
```

### Common Use: Check Even/Odd

```python
x = int(input("Number: "))

if x % 2 == 0:
    print("Even")
else:
    print("Odd")
```

**How it works:**
- Even numbers divided by 2 have remainder 0
- Odd numbers divided by 2 have remainder 1

### Other Uses

```python
# Check if divisible by 3
if x % 3 == 0:
    print("Divisible by 3")

# Get last digit
last_digit = x % 10

# Check if leap year (simplified)
if year % 4 == 0:
    print("Might be a leap year")
```

---

## Boolean Values

**Booleans** are `True` or `False` values.

### Creating Booleans

```python
is_student = True
has_passed = False

# From comparisons
is_adult = age >= 18
is_weekend = day == "Saturday" or day == "Sunday"
```

### Using Booleans in Conditionals

```python
is_raining = True

if is_raining:
    print("Take an umbrella")

# Same as:
if is_raining == True:
    print("Take an umbrella")
```

> **Pro Tip:** Just use `if is_raining:` instead of `if is_raining == True:`

### Checking for False

```python
is_logged_in = False

# Pythonic way
if not is_logged_in:
    print("Please log in")

# Also works (but less Pythonic)
if is_logged_in == False:
    print("Please log in")
```

---

## Pythonic Conditionals

**Pythonic** means writing code the Python way—clean, readable, and idiomatic.

### 1. Chained Comparisons

```python
# ❌ Not Pythonic
if x > 0 and x < 10:
    print("Single digit positive")

# ✅ Pythonic
if 0 < x < 10:
    print("Single digit positive")
```

```python
# Check if in range
age = 25

if 18 <= age <= 65:
    print("Working age")
```

### 2. Multiple Equality Checks

```python
# ❌ Verbose
if answer == "yes" or answer == "y" or answer == "Y":
    print("Confirmed")

# ✅ Pythonic
if answer in ["yes", "y", "Y"]:
    print("Confirmed")
```

### 3. Checking String Methods

```python
name = input("Name: ")

# ❌ Not needed
if name.lower() == name.lower():

# ✅ Pythonic - check directly
if name.islower():
    print("All lowercase")

if name.isupper():
    print("All uppercase")

if name.isalpha():
    print("Only letters")
```

### 4. Ternary Operator (One-line if-else)

```python
# Regular if-else
if x > 0:
    result = "positive"
else:
    result = "non-positive"

# ✅ Ternary operator
result = "positive" if x > 0 else "non-positive"
```

**Syntax:** `value_if_true if condition else value_if_false`

```python
# More examples
age = 20
status = "adult" if age >= 18 else "minor"

score = 85
grade = "Pass" if score >= 60 else "Fail"

# Even in print statements
print("Even" if x % 2 == 0 else "Odd")
```

---

## Match Statements

**Match statements** (Python 3.10+) are like switch/case in other languages.

### Basic Syntax

```python
match variable:
    case value1:
        # Code for value1
    case value2:
        # Code for value2
    case _:
        # Default case (like else)
```

### Example 1: Simple Menu

```python
choice = input("Choose (a/b/c): ")

match choice:
    case "a":
        print("You chose A")
    case "b":
        print("You chose B")
    case "c":
        print("You chose C")
    case _:
        print("Invalid choice")
```

### Example 2: Harry Potter Houses

```python
name = input("What's your name? ")

match name:
    case "Harry" | "Hermione" | "Ron":
        print("Gryffindor")
    case "Draco":
        print("Slytherin")
    case _:
        print("Who?")
```

**Note:** The `|` means "or" in match statements

### If-Elif vs Match

**Using if-elif:**
```python
house = input("House: ")

if house == "Gryffindor":
    print("🦁")
elif house == "Hufflepuff":
    print("🦡")
elif house == "Ravenclaw":
    print("🦅")
elif house == "Slytherin":
    print("🐍")
else:
    print("❓")
```

**Using match:**
```python
house = input("House: ")

match house:
    case "Gryffindor":
        print("🦁")
    case "Hufflepuff":
        print("🦡")
    case "Ravenclaw":
        print("🦅")
    case "Slytherin":
        print("🐍")
    case _:
        print("❓")
```

> **Pro Tip:** Use `match` when comparing one variable against multiple values. Use `if-elif` for complex conditions.

---

## Practice Exercises

### Exercise 1: Age Classifier 🌱
**Objective:** Classify age into child, teen, adult, senior

**Requirements:**
- Child: 0-12
- Teen: 13-19
- Adult: 20-64
- Senior: 65+

<details>
<summary>Click to see solution</summary>

```python
age = int(input("Age: "))

if age < 0:
    print("Invalid age")
elif age <= 12:
    print("Child")
elif age <= 19:
    print("Teen")
elif age <= 64:
    print("Adult")
else:
    print("Senior")
```
</details>

### Exercise 2: Leap Year Checker 🌿
**Objective:** Determine if a year is a leap year

**Rules:**
- Divisible by 4: leap year
- UNLESS divisible by 100: not a leap year
- UNLESS divisible by 400: leap year

<details>
<summary>Click to see solution</summary>

```python
year = int(input("Year: "))

if year % 400 == 0:
    print("Leap year")
elif year % 100 == 0:
    print("Not a leap year")
elif year % 4 == 0:
    print("Leap year")
else:
    print("Not a leap year")
```
</details>

### Exercise 3: Temperature Advisor 🌳
**Objective:** Give clothing advice based on temperature

**Ranges:**
- Below 0°C: "Freezing! Heavy coat needed"
- 0-15°C: "Cold. Wear a jacket"
- 16-25°C: "Nice! Light clothing"
- Above 25°C: "Hot! Stay hydrated"

<details>
<summary>Click to see solution</summary>

```python
temp = int(input("Temperature (°C): "))

if temp < 0:
    print("Freezing! Heavy coat needed")
elif temp <= 15:
    print("Cold. Wear a jacket")
elif temp <= 25:
    print("Nice! Light clothing")
else:
    print("Hot! Stay hydrated")
```
</details>

### Exercise 4: Password Validator 🌲
**Objective:** Check if password meets requirements

**Requirements:**
- At least 8 characters
- Contains at least one number

<details>
<summary>Click to see solution</summary>

```python
password = input("Enter password: ")

if len(password) >= 8 and any(char.isdigit() for char in password):
    print("Valid password")
else:
    print("Invalid password")
    if len(password) < 8:
        print("- Too short (minimum 8 characters)")
    if not any(char.isdigit() for char in password):
        print("- Must contain at least one number")
```
</details>

### Exercise 5: BMI Calculator 🌲
**Objective:** Calculate BMI and classify health status

**Formula:** BMI = weight(kg) / height(m)²

**Categories:**
- Below 18.5: Underweight
- 18.5-24.9: Normal
- 25-29.9: Overweight
- 30+: Obese

<details>
<summary>Click to see solution</summary>

```python
weight = float(input("Weight (kg): "))
height = float(input("Height (m): "))

bmi = weight / (height ** 2)

print(f"Your BMI is {bmi:.1f}")

if bmi < 18.5:
    print("Category: Underweight")
elif bmi < 25:
    print("Category: Normal")
elif bmi < 30:
    print("Category: Overweight")
else:
    print("Category: Obese")
```
</details>

---

## Key Takeaways 🎯

✅ **if** executes code when condition is `True`  
✅ **elif** checks additional conditions  
✅ **else** runs when all conditions are `False`  
✅ **and** requires all conditions to be `True`  
✅ **or** requires at least one condition to be `True`  
✅ **not** negates a condition  
✅ **match** compares one variable against multiple values  
✅ Use `==` for comparison, `=` for assignment  

---

## Common Mistakes to Avoid ⚠️

| Mistake | Problem | Solution |
|---------|---------|----------|
| `if x = 5:` | Using `=` instead of `==` | Use `if x == 5:` |
| Missing colon | `if x > 5` | Add colon: `if x > 5:` |
| Wrong indentation | Code not inside if block | Use 4 spaces/1 tab |
| `if x == 5 or 6:` | Doesn't check both values | Use `if x == 5 or x == 6:` |
| Multiple conditions without `and`/`or` | Logic error | Use `if x > 0 and x < 10:` |

---

## Comparison: If-Elif vs Multiple Ifs

### Multiple If Statements
```python
score = 85

if score >= 90:
    print("A")
if score >= 80:  # Still checks this!
    print("B")
if score >= 70:  # And this!
    print("C")

# Output: B and C (wrong!)
```

### If-Elif (Correct)
```python
score = 85

if score >= 90:
    print("A")
elif score >= 80:  # Only checks if previous was False
    print("B")
elif score >= 70:  # Only checks if both above were False
    print("C")

# Output: B (correct!)
```

---

## Next Steps 🚀

Ready to practice? Try these challenges:
1. Create a simple calculator that asks for operation (+, -, *, /) and two numbers
2. Build a login system that checks username AND password
3. Make a quiz program with multiple questions and score tracking
4. Create a ticket pricing system (child/adult/senior with different prices)

---

**Happy Coding!** 🎉

*These notes are part of CS50's Introduction to Programming with Python*
