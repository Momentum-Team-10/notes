# Welcome to Phase 2
## Intro to Backend Development with Python & Django

---

## Python Origins

- General purpose programming language developed by Guido van Rossum and released in 1991.

### Stated Goals

    1. an easy and intuitive language just as powerful as those of the major competitors;
    2. open source, so anyone can contribute to its development;
    3. code that is as understandable as plain English;
    4. suitable for everyday tasks, allowing for short development times.

---

## Let's write some Python and see what happens.

Copy this code in an empty Python file, but do not run it.

Predict what you think will happen.

Then, run it and check your expectations against what happens.

```py

def greet(names):
    for name in names:
        print(f"Hi, {name}!")

our_names = ["Amy", "Jeanette", "Rebecca", "Dawn", "Dwayne 'The Rock' Johnson"]

greet(our_names)
```

---

## Python/JavaScript Comparison

| JavaScript                             | Python                        |
| -------------------------------------- | ----------------------------- |
| Array (push)                           | List (append)                 |
| `function`                             | `def()`                       |
| White space NBD                        | White space conveys meaning   |
| `let`/`const` declare variables        | variables not declared        |
| `if/while (condition) { outcome }`     | `if/while condition: outcome` |
| `for (let i of array) { function(i) }` | f`or i in list: f(i)`         |

---

## Try some more Python.

```py

def sum(numbers):
    numbers_copy = numbers.copy()
    sum = 0
    while len(numbers_copy) > 0:
        sum += numbers[len(numbers_copy) - 1]
        numbers_copy.pop()
    print(sum)
    return(sum)

my_sum = sum([1, 2, 3, 17])
```

---

## Quick reference for Python syntax

```py
# variables
var_name = value

# functions
def my_function(parameter1, parameter2):
    # here's where the action happens
    return value_to_be_returned

# to see values in the console
print(value)

# conditionals
if a > b:
    return(a)

# loops
while b < a:
    b += 1

for item in my_list:
   # do something to the item

# remember to use snake_case instead of camelCase
```

---
