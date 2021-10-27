

## 💡 To run this code, type `python` at the command line prompt.

That will start a Python REPL where you can run Python code! Good practice would be to type this in there and see what you get.

Don't type the `>>>`. That is showing you the start of the prompt in the Python REPL.

# Python Lists

### Collections enclosed by `[]`

They are indexed like JS arrays and trailing commas can be used.

```py
>>> nerf_guns = ['Rampage', 'Shockwave RD-15', 'Mediator',]
>>> my_list[0]
'Rampage'
```

### Examples of frequently used list methods

- `append()`
- `pop()`
- `remove()`

```py
>>> nerf_guns.append('Jolt')
>>> nerf_guns
['Rampage', 'Shockwave RD-15', 'Mediator', 'Jolt']
>>> nerf_guns.pop() # this gives you back the thing you popped off the list, and alters the list
'Jolt'
>>> nerf_guns
['Rampage', 'Shockwave RD-15', 'Mediator']
>>> nerf_guns.remove('Mediator') # this does not return the thing you removed, but it does change the list
>>> nerf_guns
['Rampage', 'Shockwave RD-15']
```

---

# Python Dictionaries

### _key: value_ pairs enclosed by `{}`

Similar to JS objects.

Notice that you need to put quotation marks around the keys, unlike in JS objects (but like JSON!).

Trailing commas also 👍 in dictionaries, as in lists.

```py
>>> fruit_amounts = {
    'apples': 3,
    'bananas': 4,
    'papayas': 2,
    }
```

### Obtain values by their keys, NOT their position

You have to use square brackets enclosing a string to retrieve values by their key.

⚠️ **Dot notation will not work like it does in JS.**

```py
>>> fruit_amounts['apples']
3
```

---

### Add or reassign values to dictionaries

```py
>>> fruit_amounts['pears'] = 5
>>> fruit_amounts['bananas'] = 10
>>> fruit_amounts
{'apples': 3, 'bananas': 10, 'papayas': 2, 'pears': 5}
```

Notice you can change values for existing keys and add new keys with their values **with the same syntax**.

---

# Python Tuples

### Ordered collections enclosed by `()`

Tuples are like lists but they are immutable (can't be changed).

```py
>>> dimensions = (2, 4, 10)
```

### Obtain data using index, as with lists

```py
>>> dimensions[1]
4
```

---

### Unpack tuples by assigning each value to a variable

```py
>>> length, width, height = (2, 4, 10)
>>> length
2
>>> width
4
>>> height
10
```

---
