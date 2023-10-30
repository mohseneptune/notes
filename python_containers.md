# Python Containers

Python provides a variety of containers, data structures that hold and organize other objects. These containers are essential for managing and processing data efficiently. In this section, we'll explore some of the most common Python containers and understand how they work.

## Lists

A list is a versatile container that can store an ordered collection of items. It is mutable, meaning you can change its content by adding, removing, or modifying elements. Lists are created using square brackets.

**Explanation**: Lists are used when you need an ordered collection of items, and you anticipate making changes to the data over time.

**Example**:
```python
fruits = ["apple", "banana", "cherry"]
numbers = [1, 2, 3, 4, 5]
```

## Tuples

Tuples are similar to lists but are immutable, meaning their contents cannot be changed once defined. They are created using parentheses.

**Explanation**: Tuples are used when you need a collection of items that should not change. They are often used for representing data that should remain constant.

**Example**:
```python
coordinates = (3, 4)
colors = ("red", "green", "blue")
```

## Dictionaries

Dictionaries are collections of key-value pairs, where each key is associated with a value. They are created using curly braces and colons.

**Explanation**: Dictionaries are used when you need to store data in a structured way and access it quickly using keys.

**Example**:
```python
person = {"name": "Alice", "age": 30, "city": "Wonderland"}
product_prices = {"apple": 0.99, "banana": 0.75, "cherry": 1.25}
```

## Sets

Sets are collections of unique elements with no specific order. They are created using curly braces or the `set()` constructor.

**Explanation**: Sets are used when you need to work with a unique set of elements, often for tasks like removing duplicates or checking for membership.

**Example**:
```python
fruits = {"apple", "banana", "cherry"}
numbers = set([1, 2, 3, 4, 5, 3])  # Using set() to remove duplicates
```

## Lists of Lists

A list of lists is a container where each element is a list. This is used for representing data in a two-dimensional manner.

**Explanation**: Lists of lists are used when you need to represent data with multiple dimensions, such as a matrix.

**Example**:
```python
matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
```

## NamedTuples

A `namedtuple` is a subclass of a tuple with named fields. It combines the immutability of tuples with the readability of dictionaries.

**Explanation**: NamedTuples are used when you want to create simple classes for storing data, such as for representing points in 2D space.

**Example**:
```python
from collections import namedtuple

Point = namedtuple("Point", ["x", "y"])
p = Point(3, 4)
```