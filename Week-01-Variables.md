# CS50 Python - Week 1: Variables

## What are Variables?

Variables are like labeled boxes that store data in your program. Think of them as containers with names that hold different types of information.

```python
name = "Alice"        # A box labeled "name" containing "Alice"
age = 20             # A box labeled "age" containing 20
height = 5.6         # A box labeled "height" containing 5.6
```

## Variable Naming Rules

### ✅ Valid Names:
- Must start with a letter (a-z, A-Z) or underscore (_)
- Can contain letters, numbers, and underscores
- Case-sensitive (`name` ≠ `Name`)

```python
first_name = "John"    # Good: descriptive, uses underscore
age2 = 25             # Good: letter then number
_private = "secret"    # Good: starts with underscore
```

### ❌ Invalid Names:
```python
2name = "John"        # Bad: starts with number
first-name = "John"   # Bad: contains hyphen
class = "CS50"        # Bad: reserved keyword
```

## Python Data Types

### 1. Strings (str)
Text data enclosed in quotes

```python
name = "David Malan"
message = 'Hello, world!'
multiline = """This is a
long message"""

# String operations
greeting = "Hello"
name = "Alice"
full_greeting = greeting + ", " + name  # Concatenation
print(f"Welcome, {name}!")              # f-string formatting
```

### 2. Integers (int)
Whole numbers (positive, negative, or zero)

```python
students = 800
temperature = -5
zero = 0

# Math operations
x = 10
y = 3
print(x + y)    # Addition: 13
print(x - y)    # Subtraction: 7
print(x * y)    # Multiplication: 30
print(x / y)    # Division: 3.333...
print(x // y)   # Floor division: 3
print(x % y)    # Modulo (remainder): 1
print(x ** y)   # Exponentiation: 1000
```

### 3. Floats (float)
Decimal numbers

```python
pi = 3.14159
gpa = 3.75
price = 19.99

# Be careful with float precision!
result = 0.1 + 0.2  # Might not exactly equal 0.3
```

### 4. Booleans (bool)
True or False values

```python
is_student = True
is_graduated = False

# Boolean operations
hungry = True
tired = False
print(hungry and tired)    # False
print(hungry or tired)     # True
print(not hungry)          # False
```

## Getting User Input

```python
name = input("What's your name? ")
age = input("How old are you? ")        # Returns string!
age_number = int(age)                   # Convert to integer

# Better approach:
age = int(input("How old are you? "))
```

## Type Conversion

```python
# String to number
age_str = "20"
age_int = int(age_str)      # String to integer
price_float = float("19.99") # String to float

# Number to string
count = 42
count_str = str(count)      # Integer to string

# Check types
print(type(name))           # <class 'str'>
print(type(age))            # <class 'int'>
```

## Common Mistakes to Avoid

```python
# ❌ Forgetting quotes around strings
name = Alice              # Error: NameError

# ❌ Trying to do math with strings
age = "20"
next_year = age + 1       # Error: can't add string and int

# ✅ Convert first
age = int("20")
next_year = age + 1       # Works: 21

# ❌ Using reserved words as variables
print = "Hello"           # Don't do this!
# Now print() function won't work
```

## Best Practices

1. **Use descriptive names:** `student_count` not `sc`
2. **Follow snake_case:** `first_name` not `firstName`
3. **Initialize variables:** Give them values when you create them
4. **Be consistent:** Pick a naming style and stick to it

## Key Functions to Remember

```python
print()         # Output to screen
input()         # Get user input (always returns string)
int()          # Convert to integer
float()        # Convert to float
str()          # Convert to string
type()         # Check data type
len()          # Get length of string
```

## Practice Exercise

**Challenge:** Create a simple program that:
1. Asks for the user's name
2. Asks for their age
3. Calculates what their age will be in 10 years
4. Displays a personalized message

Try it yourself first, then check the solution below!

<details>
<summary>Click to see solution</summary>

```python
# Get user information
name = input("What's your name? ")
age = int(input("What's your age? "))

# Calculate future age
future_age = age + 10

# Display result
print(f"Hello, {name}!")
print(f"In 10 years, you'll be {future_age} years old!")
```

</details>

---

**Next:** [Week 2 - Conditionals](Week-02-Conditionals.md)

---

> 💡 **Study Tip:** Try modifying the practice exercise! What if you calculated their age in 5 years? Or asked for their birth year instead?
