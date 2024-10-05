### Why is Python called interpreted Language?
- Executes instructions directly and line by line
- Does not compile and run a complete program at once
- When it encounters an errors, it stops
- This makes Python easier to debug
- Python doesn't need a separate compilation step.

### What are the built-in data types in Python?
* Text Type: str
* Numeric Types: int, float, complex numbers
* Sequence Types: list, tuple, range
* Map Type: dictionary
* Set Type: set, frozenset
* Boolean Type: bool
* Binary types: bytes, bytearray, memoryview
* NoneType: NoneType

### What are the differences between list and tuple and set?
* Tuples are immutable objects, lists are mutable
* Once defined, tuples have a fixed length and lists have a dynamic length
* Tuples uses less memory and are faster to access than to lists
* Sets are mutable, but unordered collection and has no duplicate elements
* Items in set cannot be changed or replaced but you can remove and add new items.

### Difference between dictionary and JSON?
* JSON keys can only be strings whereas dictionary keys can be hashable objects
* Keys are ordered sequentially and can be repeated in JSON, but in dictionary keys can not be repeated and must be distinct

### What is the differences between modules and packages?
* A module in Python is simply a .py file containing Python code
* Package is a collection of modules

### Explain the use of lambda expressions in Python. When is it useful?
* lamda is basically a function without a name
* useful in situations where you need a small temporary function and where you need to pass a function as a parameter
```
// a regular function
def add(x,y)
    return(x+y)

// a lambda function
add2 = lambda x,y: x+y
```

### Explain slicing in Python
* Slicing allows you to access a subset or a "slice" of a list
* Slice specifies a start index and an end index of a list

### What is shallow copy and deep copy in Python.
* Shallow copy stores the reference of the original elements where deep copy creates new objects which contains all the data of original elements

### What is inheritance in Python, explain single inheritance and multiple inheritance.

### What is decorators?
* Decorators are a special kind of function that add extra functionality to another function

### Explain the difference between "is" and "=="?
* "==" checks only values are equal or not where "is" operator checks reference with values


