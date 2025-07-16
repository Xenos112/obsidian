---
tags:
  - python
---

# Python Variables Guide
## Table of Contents
- [[#What are Variables?|What are Variables?]]
	- [[#What are Variables?#Key Points About Variables:|Key Points About Variables:]]
	- [[#What are Variables?#Basic Variable Declaration:|Basic Variable Declaration:]]
	- [[#What are Variables?#Using Variables:|Using Variables:]]
- [[#Types of Variables in Python|Types of Variables in Python]]
	- [[#Types of Variables in Python#1. String (`str`)|1. String (`str`)]]
	- [[#Types of Variables in Python#Examples:|Examples:]]
	- [[#Types of Variables in Python#String Tips:|String Tips:]]
	- [[#Types of Variables in Python#2. Integer (`int`)|2. Integer (`int`)]]
	- [[#Types of Variables in Python#Examples:|Examples:]]
	- [[#Types of Variables in Python#3. Float (`float`)|3. Float (`float`)]]
	- [[#Types of Variables in Python#Examples:|Examples:]]
	- [[#Types of Variables in Python#4. Boolean (`bool`)|4. Boolean (`bool`)]]
	- [[#Types of Variables in Python#Examples:|Examples:]]
	- [[#Types of Variables in Python#Boolean Tips:|Boolean Tips:]]
	- [[#Types of Variables in Python#5. None Type (`NoneType`)|5. None Type (`NoneType`)]]
	- [[#Types of Variables in Python#Examples:|Examples:]]
	- [[#Types of Variables in Python#None Tips:|None Tips:]]
- [[#Variable Naming Best Practices|Variable Naming Best Practices]]
- [[#Quick Type Checking|Quick Type Checking]]
- [[#Summary|Summary]]

---
## What are Variables?
Variables are containers that store data values for later use in your program. Think of them as labeled boxes where you can put different types of information.

### Key Points About Variables:
- Each variable should have a unique name
- When you assign a new value to an existing variable name, it replaces the previous value
- Variables are created by simply assigning a value to a name

### Basic Variable Declaration:

```python
number = 12
text = "Hello, World!"
is_active = True

```

### Using Variables:
```python
message = "Welcome to Python!"
print(message)  # Output: Welcome to Python!

```

## Types of Variables in Python
Python has several built-in data types. Here are the most common ones:

### 1. String (`str`)
Strings represent text data and must be wrapped in single quotes `'` or double quotes `"`.

### Examples:
```python
# Valid ✅
name = "Alice"
greeting = 'Hello there!'
message = "Python is awesome"

# Invalid ❌
# invalid_text = Hello World  # Missing quotes
# mixed_quotes = 'This is wrong"  # Mismatched quotes

```

### String Tips:
- Use consistent quote style throughout your code
- You can use single quotes inside double quotes and vice versa
- For multi-line strings, use triple quotes: `"""` or `'''`

### 2. Integer (`int`)
Integers are whole numbers without decimal points.

### Examples:
```python
age = 25
count = 0
negative_number = -10
large_number = 1000000

# Note: If you wrap numbers in quotes, they become strings
age_as_string = "25"  # This is a string, not an integer

```

### 3. Float (`float`)
Floats are numbers with decimal points.

### Examples:
```python
price = 19.99
temperature = -3.5
pi = 3.14159
percentage = 0.85

```

### 4. Boolean (`bool`)
Booleans represent True or False values. They're useful for conditions and logical operations.

### Examples:
```python
is_student = True
is_weekend = False
has_permission = True
is_complete = False

# Common use cases
if is_student:
    print("Student discount applied!")

while not is_complete:
    print("Still working...")
    # ... some code ...
    is_complete = True

```

### Boolean Tips:
- Always capitalize: `True` and `False` (not `true` or `false`)
- Booleans are often the result of comparisons: `age >= 18` returns `True` or `False`

### 5. None Type (`NoneType`)
`None` represents the absence of a value. It's Python's way of saying "nothing" or "no value."

### Examples:
```python
result = None
user_input = None
optional_data = None

# Common use cases
def find_user(username):
    # If user not found, return None
    if username not in users:
        return None
    return users[username]

# Checking for None
if result is None:
    print("No result found")
else:
    print(f"Result: {result}")

```

### None Tips:
- Use `is None` or `is not None` to check for None values
- `None` is not the same as `0`, `False`, or an empty string `""`

## Variable Naming Best Practices
```python
# Good variable names ✅
user_name = "john doe"
total_price = 29.99
is_logged_in = True
MAX_ATTEMPTS = 3  # Constants in UPPER_CASE

# Avoid these naming patterns ❌
# x = "john_doe"  # Not descriptive
# 123abc = "value"  # Can't start with numbers
# user-name = "john"  # Hyphens not allowed
# class = "Python"  # Don't use reserved keywords

```

## Quick Type Checking
You can check the type of any variable using the `type()` function:

```python
name = "Alice"
age = 30
height = 5.8
is_student = True
data = None

print(type(name))       # <class 'str'>
print(type(age))        # <class 'int'>
print(type(height))     # <class 'float'>
print(type(is_student)) # <class 'bool'>
print(type(data))       # <class 'NoneType'>

```

## Summary
Variables are fundamental building blocks in Python programming. Understanding these five basic types (string, integer, float, boolean, and None) will help you store and manipulate data effectively in your programs. Remember to use descriptive names and follow Python's naming conventions for clean, readable code!