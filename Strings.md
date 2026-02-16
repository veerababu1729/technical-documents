# Python Strings - Complete Guide

## What is a String?

Strings are nothing but a word, a sentence, or a number surrounded by either single quotation marks or double quotation marks in Python.

Examples:
- 'hello' is a string
- "hello" is also a string
- "12345" is a string
- 'Python Programming' is a string

---

## String Creation and Printing

You can create strings in multiple ways:

```python
# Using single quotes
name = 'Python'

# Using double quotes
language = "Python Programming"

# Using triple quotes for multi-line strings
message = '''This is a
multi-line
string'''

# Printing strings
print(name)
print(language)
```

---

## Operations on Strings

### 1. Accessing Characters in Strings

Strings in Python use indexing to access individual characters. Python supports both positive and negative indexing.

**Positive Indexing** (starts from 0):
```python
s = "Python"
print(s[0])   # P
print(s[1])   # y
print(s[5])   # n
```

**Negative Indexing** (starts from -1 from the end):
```python
s = "Python"
print(s[-1])  # n
print(s[-6])  # P
```

### 2. String Slicing

String slicing means extracting a part or a portion of a string.

**Syntax:**
```
string[start : end : step]
```

- **start** → starting index (included)
- **end** → ending index (excluded)
- **step** → steps to jump (optional)

**Examples:**

```python
s = "HelloWorld"

# Basic slicing
print(s[0:5])    # Hello (first 5 characters)
print(s[5:10])   # World (last 5 characters)

# Slicing with step
print(s[0:10:2]) # HloWrd (every 2nd character)

# Omitting start or end
print(s[:5])     # Hello (from beginning to index 5)
print(s[5:])     # World (from index 5 to end)

# Reversing a string
print(s[::-1])   # dlroWolleH
```

### 3. Basic Operations

#### Concatenation (+)

Joining two or more strings together.

```python
s1 = "Hello"
s2 = "World"
result = s1 + " " + s2
print(result)  # Hello World
```

#### Repetition (*)

Repeating a string multiple times.

```python
s = "Python"
print(s * 3)   # PythonPythonPython

s = "Ha"
print(s * 5)   # HaHaHaHaHa
```

#### Membership (in)

Checking if a substring exists in a string.

```python
s = "Coding is fun"
print("fun" in s)      # True
print("boring" in s)   # False
print("Coding" in s)   # True
```

#### Length (len())

Finding the length of a string.

```python
s = "Python"
print(len(s))  # 6

message = "Hello World"
print(len(message))  # 11
```

---

## String Built-in Methods

### 1. Case Changing Methods

**upper()** - Converts all characters to uppercase
```python
s = "python"
print(s.upper())  # PYTHON
```

**lower()** - Converts all characters to lowercase
```python
s = "PYTHON"
print(s.lower())  # python
```

**title()** - Converts first character of each word to uppercase
```python
s = "python programming"
print(s.title())  # Python Programming
```

**capitalize()** - Converts first character to uppercase, rest to lowercase
```python
s = "python PROGRAMMING"
print(s.capitalize())  # Python programming
```

**swapcase()** - Swaps case (upper to lower, lower to upper)
```python
s = "Python"
print(s.swapcase())  # pYTHON
```

### 2. Trimming and Padding

#### Trimming Methods

**strip()** - Removes leading and trailing whitespace
```python
s = "   Python   "
print(s.strip())  # Python
```

**lstrip()** - Removes leading whitespace
```python
s = "   Python   "
print(s.lstrip())  # "Python   "
```

**rstrip()** - Removes trailing whitespace
```python
s = "   Python   "
print(s.rstrip())  # "   Python"
```

You can also remove specific characters:
```python
s = "###Python###"
print(s.strip('#'))  # Python
```

#### Padding Methods

**center(width, fillchar)** - Centers string in a field of given width
```python
s = "Python"
print(s.center(10, '*'))  # **Python**
```

**ljust(width, fillchar)** - Left-aligns string in a field of given width
```python
s = "Python"
print(s.ljust(10, '-'))  # Python----
```

**rjust(width, fillchar)** - Right-aligns string in a field of given width
```python
s = "Python"
print(s.rjust(10, '-'))  # ----Python
```

**zfill(width)** - Pads string with zeros on the left
```python
s = "42"
print(s.zfill(5))  # 00042
```

### 3. Search and Replace Methods

**find(substring)** - Returns the index of first occurrence (returns -1 if not found)
```python
s = "Python Programming"
print(s.find("Pro"))  # 7
print(s.find("Java")) # -1
```

**index(substring)** - Returns the index of first occurrence (raises error if not found)
```python
s = "Python Programming"
print(s.index("Pro"))  # 7
# print(s.index("Java"))  # Raises ValueError
```

**rfind(substring)** - Returns the index of last occurrence
```python
s = "Python Programming Python"
print(s.rfind("Python"))  # 19
```

**count(substring)** - Counts occurrences of substring
```python
s = "Python Programming Python"
print(s.count("Python"))  # 2
```

**replace(old, new)** - Replaces all occurrences of old with new
```python
s = "I love Python"
print(s.replace("Python", "JavaScript"))  # I love JavaScript

s = "hello hello hello"
print(s.replace("hello", "hi"))  # hi hi hi
```

**startswith(prefix)** - Checks if string starts with prefix
```python
s = "Python Programming"
print(s.startswith("Python"))  # True
print(s.startswith("Java"))    # False
```

**endswith(suffix)** - Checks if string ends with suffix
```python
s = "Python Programming"
print(s.endswith("ing"))    # True
print(s.endswith("Java"))   # False
```

### 4. Splitting and Joining Methods

**split(separator)** - Converts string into a list with a given separator
```python
# Example 1: Split by space (default)
s = "Python is awesome"
words = s.split()
print(words)  # ['Python', 'is', 'awesome']

# Example 2: Split by comma
s = "apple,banana,grape"
fruits = s.split(',')
print(fruits)  # ['apple', 'banana', 'grape']

# Example 3: Split by custom separator
s = "one-two-three"
items = s.split('-')
print(items)  # ['one', 'two', 'three']
```

**join(iterable)** - Joins elements of an iterable with the string as separator
```python
# Example 1: Join with space
words = ['Python', 'is', 'awesome']
s = ' '.join(words)
print(s)  # Python is awesome

# Example 2: Join with comma
fruits = ['apple', 'banana', 'grape']
s = ','.join(fruits)
print(s)  # apple,banana,grape

# Example 3: Join with hyphen
items = ['one', 'two', 'three']
s = '-'.join(items)
print(s)  # one-two-three
```

**splitlines()** - Splits string at line breaks
```python
s = "Line 1\nLine 2\nLine 3"
lines = s.splitlines()
print(lines)  # ['Line 1', 'Line 2', 'Line 3']
```

### 5. Checking String Content

**isalpha()** - Checks if all characters are alphabets
```python
print("Python".isalpha())    # True
print("Python123".isalpha()) # False
```

**isdigit()** - Checks if all characters are digits
```python
print("12345".isdigit())   # True
print("123abc".isdigit())  # False
```

**isalnum()** - Checks if all characters are alphanumeric
```python
print("Python123".isalnum())  # True
print("Python 123".isalnum()) # False (space is not alphanumeric)
```

**isspace()** - Checks if all characters are whitespace
```python
print("   ".isspace())    # True
print("  a ".isspace())   # False
```

**isupper()** - Checks if all characters are uppercase
```python
print("PYTHON".isupper())  # True
print("Python".isupper())  # False
```

**islower()** - Checks if all characters are lowercase
```python
print("python".islower())  # True
print("Python".islower())  # False
```

**istitle()** - Checks if string is in title case
```python
print("Python Programming".istitle())  # True
print("Python programming".istitle())  # False
```

---

## Important String Properties

### Strings are Immutable

Strings cannot be changed after creation. Any operation that modifies a string creates a new string.

```python
s = "Python"
# s[0] = 'J'  # This will raise an error

# Instead, create a new string
s = "J" + s[1:]
print(s)  # Jython
```

### Strings are Iterable

You can loop through strings character by character.

```python
s = "Python"
for char in s:
    print(char)
```

---

## Practice Questions

### Question 1: String Creation and Printing
Create a string variable containing your full name and print it.

### Question 2: Accessing Characters
Given `s = "Python"`, print the first and last character using positive and negative indexing.

### Question 3: String Slicing
Given `s = "HelloWorld"`, extract and print:
- First 5 characters
- Last 5 characters
- The string in reverse order

### Question 4: Concatenation and Repetition
Given `s1 = "Hello"` and `s2 = "World"`, perform and print:
- `s1 + s2`
- `s1 * 3`

### Question 5: Membership Operator
Given `s = "Coding is fun"`, check if the word "fun" is present in the string.

### Question 6: Finding Length
Write a Python program that takes a user-inputted string and prints its length using `len()`.

### Question 7: Case Changing Methods
Given `s = "pYtHoN Is AwEsOmE"`, print the string in:
- Uppercase
- Lowercase
- Title case

### Question 8: Search and Replace
Given `s = "I love Python"`, replace "Python" with "JavaScript" and print the new string.

### Question 9: Splitting and Joining
Given `s = "apple,banana,grape"`, split the string into a list and then join it back using "-" as a separator.

### Question 10: Reverse String Without Slicing
Given `s = "reverse"`, reverse the string using a loop and print it.

---

## Summary

### Key Takeaways:

1. Strings are immutable sequences of characters enclosed in quotes (single, double, or triple)
2. Python supports both positive (0-based) and negative (-1 from end) indexing
3. String slicing uses the syntax: `string[start:end:step]`
4. Basic operations include: concatenation (+), repetition (*), membership (in), and length (len())
5. Case changing methods: `upper()`, `lower()`, `title()`, `capitalize()`, `swapcase()`
6. Trimming methods: `strip()`, `lstrip()`, `rstrip()`
7. Padding methods: `center()`, `ljust()`, `rjust()`, `zfill()`
8. Search methods: `find()`, `index()`, `count()`, `startswith()`, `endswith()`
9. Replace method: `replace(old, new)`
10. Splitting: `split()`, `splitlines()`
11. Joining: `join()`
12. Content checking: `isalpha()`, `isdigit()`, `isalnum()`, `isspace()`, `isupper()`, `islower()`, `istitle()`

### Why Strings are Important:

Strings are crucial for coding interviews because:
- Most data manipulation involves string operations
- String problems test your understanding of indexing and slicing
- String methods are frequently used in real-world applications
- Many coding challenges require efficient string manipulation

Remember to practice these methods and operations regularly to master string handling in Python!
