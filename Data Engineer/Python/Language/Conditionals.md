# Python Conditions Guide 
## Table of Content
- [[#What are Conditions?|What are Conditions?]]
- [[#Basic Conditional Statements|Basic Conditional Statements]]
- [[#Comparison Operators|Comparison Operators]]
- [[#Logical Operators|Logical Operators]]
- [[#Advanced Conditional Techniques|Advanced Conditional Techniques]]
- [[#Common Patterns and Examples|Common Patterns and Examples]]
- [[#Best Practices|Best Practices]]
- [[#Common Mistakes to Avoid|Common Mistakes to Avoid]]
- [[#Summary|Summary]]

---

## What are Conditions?
Conditions in Python allow your program to make decisions based on different scenarios. They enable your code to execute different blocks of code depending on whether certain conditions are true or false. Think of them as "if this, then that" statements.

### Why Use Conditions?
- Make your programs interactive and dynamic
- Handle different user inputs
- Control program flow based on data
- Create logic that responds to changing situations

## Basic Conditional Statements
### 1. The `if` Statement
The `if` statement executes code only when a condition is `True`.

### Syntax:
```python
if condition:
    # Code to execute if condition is True
    pass

```

### Examples:
```python
age = 18

if age >= 18:
    print("You are an adult!")

# Multiple statements in if block
temperature = 30
if temperature > 25:
    print("It's hot outside!")
    print("Don't forget sunscreen!")
    print("Stay hydrated!")

```

### 2. The `if-else` Statement
The `if-else` statement provides an alternative path when the condition is `False`.

### Syntax:
```python
if condition:
    # Code if condition is True
    pass
else:
    # Code if condition is False
    pass

```

### Examples:
```python
age = 16

if age >= 18:
    print("You can vote!")
else:
    print("You cannot vote yet.")

# Another example
password = "secret123"
if password == "admin123":
    print("Access granted!")
else:
    print("Access denied!")

```

### 3. The `if-elif-else` Statement
Use `elif` (else if) to check multiple conditions in sequence.

### Syntax:
```python
if condition1:
    # Code if condition1 is True
    pass
elif condition2:
    # Code if condition2 is True
    pass
elif condition3:
    # Code if condition3 is True
    pass
else:
    # Code if none of the conditions are True
    pass

```

### Examples:
```python
grade = 85

if grade >= 90:
    print("Grade: A")
elif grade >= 80:
    print("Grade: B")
elif grade >= 70:
    print("Grade: C")
elif grade >= 60:
    print("Grade: D")
else:
    print("Grade: F")

# Weather example
weather = "sunny"
if weather == "sunny":
    print("Perfect day for a picnic!")
elif weather == "rainy":
    print("Don't forget your umbrella!")
elif weather == "snowy":
    print("Time to build a snowman!")
else:
    print("Weather is unpredictable today!")

```

## Comparison Operators
These operators are used to compare values and return `True` or `False`.

| Operator | Description           | Example           |
| -------- | --------------------- | ----------------- |
| `==`     | Equal to              | `5 == 5` → `True` |
| `!=`     | Not equal to          | `5 != 3` → `True` |
| `>`      | Greater than          | `8 > 5` → `True`  |
| `<`      | Less than             | `3 < 7` → `True`  |
| `>=`     | Greater than or equal | `5 >= 5` → `True` |
| `<=`     | Less than or equal    | `4 <= 6` → `True` |

### Examples:
```python
x = 10
y = 20

print(x == y)  # False
print(x != y)  # True
print(x > 5)   # True
print(y <= 30) # True

# Using in conditions
if x > y:
    print("x is greater than y")
elif x < y:
    print("x is less than y")
else:
    print("x equals y")

```

## Logical Operators
Logical operators combine multiple conditions.

### 1. `and` Operator
Returns `True` only if **both** conditions are `True`.

```python
age = 25
has_license = True

if age >= 18 and has_license:
    print("You can drive!")
else:
    print("You cannot drive.")

# Multiple conditions
temperature = 22
is_sunny = True
is_weekend = True

if temperature > 20 and is_sunny and is_weekend:
    print("Perfect day for outdoor activities!")

```

### 2. `or` Operator
Returns `True` if **at least one** condition is `True`.

```python
is_student = True
is_senior = False

if is_student or is_senior:
    print("You get a discount!")
else:
    print("Regular price applies.")

# Emergency contact example
is_emergency = False
is_family = True
is_friend = True

if is_emergency or is_family or is_friend:
    print("Call is allowed.")

```

### 3. `not` Operator
Reverses the boolean value (`True` becomes `False` and vice versa).

```python
is_logged_in = False

if not is_logged_in:
    print("Please log in first.")
else:
    print("Welcome back!")

# Double negative example
is_not_ready = False
if not is_not_ready:
    print("Ready to proceed!")

```

## Advanced Conditional Techniques
### 1. Nested Conditions
You can place conditions inside other conditions.

```python
weather = "sunny"
temperature = 25

if weather == "sunny":
    if temperature > 20:
        print("Perfect beach weather!")
    else:
        print("Sunny but a bit cool.")
else:
    if temperature > 20:
        print("Warm but not sunny.")
    else:
        print("Cold and not sunny.")

```

### 2. Checking Multiple Values
```python
# Check if value is in a list
favorite_color = "blue"
valid_colors = ["red", "green", "blue", "yellow"]

if favorite_color in valid_colors:
    print("Valid color choice!")
else:
    print("Please choose a valid color.")

# Check multiple possibilities
user_input = "yes"
if user_input in ["yes", "y", "YES", "Yes"]:
    print("User agreed!")
elif user_input in ["no", "n", "NO", "No"]:
    print("User declined.")
else:
    print("Please enter yes or no.")

```

### 3. Checking Data Types
```python
user_input = "25"

if isinstance(user_input, str):
    print("Input is a string")
elif isinstance(user_input, int):
    print("Input is an integer")
elif isinstance(user_input, float):
    print("Input is a float")
else:
    print("Unknown data type")

```

### 4. Checking for None and Empty Values
```python
username = ""
password = None

if username:
    print("Username provided")
else:
    print("Username is empty")

if password is None:
    print("Password not set")
elif password == "":
    print("Password is empty")
else:
    print("Password provided")

```

## Common Patterns and Examples
### 1. User Input Validation
```python
age = input("Enter your age: ")

if age.isdigit():
    age = int(age)
    if age >= 0 and age <= 120:
        print(f"Your age is {age}")
    else:
        print("Please enter a valid age between 0 and 120")
else:
    print("Please enter a valid number")

```

### 2. Grade Calculator
```python
def calculate_grade(score):
    if score >= 97:
        return "A+"
    elif score >= 93:
        return "A"
    elif score >= 90:
        return "A-"
    elif score >= 87:
        return "B+"
    elif score >= 83:
        return "B"
    elif score >= 80:
        return "B-"
    elif score >= 77:
        return "C+"
    elif score >= 73:
        return "C"
    elif score >= 70:
        return "C-"
    elif score >= 67:
        return "D+"
    elif score >= 65:
        return "D"
    else:
        return "F"

student_score = 88
grade = calculate_grade(student_score)
print(f"Score: {student_score}, Grade: {grade}")

```

### 3. Simple Calculator
```python
def simple_calculator(num1, operator, num2):
    if operator == "+":
        return num1 + num2
    elif operator == "-":
        return num1 - num2
    elif operator == "*":
        return num1 * num2
    elif operator == "/":
        if num2 != 0:
            return num1 / num2
        else:
            return "Error: Division by zero"
    else:
        return "Error: Invalid operator"

result = simple_calculator(10, "+", 5)
print(f"Result: {result}")

```

## Best Practices

### 1. Keep Conditions Simple and Readable ✅
```python
# Good
if age >= 18 and has_id:
    print("Can enter")

# Better than
if (age >= 18) and (has_id == True):
    print("Can enter")

```

### 2. Use Meaningful Variable Names ✅
```python
# Good
if is_weekend and weather == "sunny":
    print("Great day for outdoor activities!")

# Not ideal
if x and y == "sunny":
    print("Great day for outdoor activities!")

```

### 3. Handle Edge Cases ✅
```python
def divide(a, b):
    if b == 0:
        return "Cannot divide by zero"
    elif not isinstance(a, (int, float)) or not isinstance(b, (int, float)):
        return "Both arguments must be numbers"
    else:
        return a / b

```

### 4. Use Early Returns to Reduce Nesting ✅
```python
def check_access(user):
    if not user:
        return "No user provided"

    if not user.is_active:
        return "User account is inactive"

    if not user.has_permission:
        return "User lacks required permissions"

    return "Access granted"

```

## Common Mistakes to Avoid
### 1. Using Assignment Instead of Comparison ❌
```python
# Wrong
if age = 18:  # This is assignment, not comparison
    print("Adult")

# Correct
if age == 18:  # This is comparison
    print("Adult")

```

### 2. Comparing with Boolean Values ❌
```python
# Unnecessary
if is_active == True:
    print("User is active")

# Better
if is_active:
    print("User is active")

# For False checks
if not is_active:
    print("User is inactive")

```

### 3. Forgetting Indentation ❌
```python
# Wrong - no indentation
if age >= 18:
print("Adult")

# Correct - proper indentation
if age >= 18:
    print("Adult")

```

## Summary
Conditions are essential for creating dynamic and interactive Python programs. They allow your code to make decisions and respond to different situations. Remember to:

- Use proper indentation (4 spaces is Python standard)
- Keep conditions simple and readable
- Handle edge cases and invalid inputs
- Use meaningful variable names
- Test your conditions thoroughly

Master these conditional statements, and you'll be able to create programs that can think and respond intelligently to different scenarios!