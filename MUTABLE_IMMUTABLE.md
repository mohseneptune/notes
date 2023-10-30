# Mutable and Immutable Objects in Python

Python classifies objects into two main categories: mutable and immutable. Understanding the distinction between these two types is crucial for writing efficient and error-free code. In this section, we'll explore the concepts of mutable and immutable objects and how they affect your Python programs.

## Mutable Objects

Mutable objects are those whose content can be modified after they are created. This means you can change their values or attributes without creating a new object. Common examples of mutable objects in Python include:

### Lists

A list is a typical example of a mutable object. You can add, remove, or modify elements in a list.

**Explanation**: Lists are mutable and are used when you need an ordered collection of items that you can change over time.

**Example**:
```python
fruits = ["apple", "banana", "cherry"]
fruits.append("date")  # Modifying the list
```

### Dictionaries

Dictionaries are mutable containers that store key-value pairs. You can add, remove, or update key-value pairs in a dictionary.

**Explanation**: Dictionaries are mutable and are used for quick access to data using keys, which can be modified.

**Example**:
```python
person = {"name": "Alice", "age": 30}
person["age"] = 31  # Modifying a dictionary value
```

### Sets

Sets are mutable containers that store unique elements. You can add and remove elements from a set.

**Explanation**: Sets are mutable and are used for working with collections of unique items that can change.

**Example**:
```python
fruits = {"apple", "banana", "cherry"}
fruits.add("date")  # Modifying the set
```

## Immutable Objects

Immutable objects, on the other hand, cannot be modified once they are created. Any operation that appears to modify an immutable object actually creates a new object. Common examples of immutable objects in Python include:

### Strings

Strings are a classic example of an immutable object. You cannot change the characters in a string; you create a new string instead.

**Explanation**: Strings are immutable and are used for representing text that should not change.

**Example**:
```python
text = "Hello, World!"
new_text = text.replace("World", "Universe")  # Creating a new string
```

### Tuples

Tuples are also immutable objects. You cannot modify the elements in a tuple; you create a new tuple instead.

**Explanation**: Tuples are immutable and are used for representing collections of items that should not change.

**Example**:
```python
coordinates = (3, 4)
new_coordinates = (5, 6)  # Creating a new tuple
```

### NamedTuples

NamedTuples, from the `collections` module, are a type of tuple, so they are also immutable. Fields cannot be modified; you create a new NamedTuple instead.

**Explanation**: NamedTuples are immutable and are used for creating simple classes for storing data.

**Example**:
```python
from collections import namedtuple

Point = namedtuple("Point", ["x", "y"])
p = Point(3, 4)
p = Point(5, 6)  # Creating a new NamedTuple
```