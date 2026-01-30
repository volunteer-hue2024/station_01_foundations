This guide summarizes the core differences between Python's primary collection types: **Lists**, **Tuples**, and **Sets**.

---

##  Python Collections 
### 1. Quick Syntax Comparison

Each collection type is defined by a specific set of brackets:

| Type | Syntax | Example |
| --- | --- | --- |
| **List** | Square Brackets `[]` | `my_list = ["A", "B", "C", "A"]` |
| **Tuple** | Parentheses `()` | `my_tuple = ("A", "B", "C", "A")` |
| **Set** | Curly Braces `{}` | `my_set = {"A", "B", "C"}` |

---

### 2. Key Characteristics

#### **Duplicates & Uniqueness**

* **Lists & Tuples:** Allow duplicate values. They keep every item exactly as you entered it.
* **Sets:** Automatically filter out duplicates. They only store **unique** items.
* *Tip:* You can remove duplicates from a list by converting it to a set: `list(set(my_list))`.



#### **Ordering & Indexing**

* **Ordered (Lists & Tuples):** Items have :point_right: a fixed position. You can access them using an index (e.g., `my_list[0]`).
* **Unordered (Sets):** Items have no fixed position. You cannot access items via an index; attempting to do so will raise a `TypeError`.

#### **Mutability (Changeability)**

* **Mutable (Lists & Sets):** You can modify these after creation. You can `append()` to lists or `add()` to sets.
* **Immutable (Tuples):** Once a tuple is created, it cannot be changed. This makes them faster and safer for data that should remain constant.

### 4. When to Use Which?

* **Use a List** when you need a collection of items that might change or where the order of items matters (e.g., a "To-Do" list).
* **Use a Tuple** for data that should be "read-only," such as a person's **birthday** or GPS coordinates (Latitude, Longitude).
* **Use a Set** when you need to ensure all items are unique or when you want to perform mathematical operations like intersections or unions.

---


Here is how you can implement those conversions and operations in Python. 

###  Practical Examples

#### **1. Converting Between Types**

The most common use case for sets is removing duplicates from a list.

```python
# A list with duplicate values
data_list = ["apple", "banana", "apple", "orange", "banana"]

# Convert to set to remove duplicates
unique_data = set(data_list)
# Result: {'orange', 'apple', 'banana'}

# Convert back to a list if you need to index it
final_list = list(unique_data)

```

---

#### **2. Protecting Data with Tuples**

Use a tuple when you want to ensure the values remain "locked" throughout your program.

```python
# Storing a coordinate that should not be changed
location = (40.7128, -74.0060) 

# This will raise a TypeError:
# location[0] = 41.0 

```

---

#### **3. Set Operations (Unique to Sets)**

Sets allow for powerful mathematical comparisons that lists cannot do easily.

```python
developers = {"Alice", "Bob", "Charlie"}
managers = {"Charlie", "David"}

# Intersection: Who is both a developer AND a manager?
both = developers.intersection(managers) # {'Charlie'}

# Difference: Who is a developer but NOT a manager?
devs_only = developers.difference(managers) # {'Alice', 'Bob'}

```
While Lists, Tuples, and Sets are the "Big Three," Python has several other specialized collections that are essential for specific tasks.

The most important one you'll encounter next is the **Dictionary**
---

## 1. Dictionaries (`dict`)

A dictionary is a collection of **Key-Value pairs**. Instead of an index (0, 1, 2), you use a unique "key" to look up a "value."

* **Syntax:** `my_dict = {"name": "Alice", "age": 25}`
* **Best for:** Storing structured data (like a user profile or database record).
* **Key Feature:** Fast lookups. Finding a value by its key is nearly instantaneous, even in massive dictionaries.

---

## 2. Named Tuples (`collections.namedtuple`)

## 3. Deque (`collections.deque`)

```

Short for "Double-Ended Queue." While you *can* add/remove items from the beginning of a list, it is very slow (). A **deque** is optimized for adding and removing items from **both ends** extremely fast ().
```
## 4. Counter (`collections.Counter`)

This is a specialized dictionary designed specifically for counting things.

## 5. Ordered Dict & Default Dict

### Summary 

| Collection | Format | Primary Strength |
| --- | --- | --- |
| **Dictionary** | `{"key": "value"}` | Labelled data & fast lookup |
| **NamedTuple** | `Point(x=1, y=2)` | Memory efficient & readable |
| **Deque** | `deque([1, 2, 3])` | High-speed adds/removes at ends |
| **Counter** | `Counter('abcac')` | Frequency tracking |
----
⚠️ 1. Map()
⚠️ 2. List Comprehensions
⚠️ 3. Lambda
----
:sunglasses:MAP
In Python, `map()` is a built-in **higher-order function** that allows you to transform every item in an iterable (like a list or tuple) without writing a manual `for` loop.
---

## 1. How it Works

The `map()` function takes two primary arguments:

1. **A Function:** The logic you want to apply.
2. **An Iterable:** The data you want to transform.

It "maps" the function onto every single element of the data.

---

## 2. Basic Syntax

```python
map(function, iterable)

```

> **Important:** `map()` returns a **map object** (an iterator). To see the results as a familiar list, you must wrap it in the `list()` constructor.

---

## 3. Example: Using a Regular Function

Suppose you want to calculate the length of every word in a list.

```python
words = ["apple", "banana", "cherry"]

# Apply the len() function to every item in the list
word_lengths = list(map(len, words))

print(word_lengths) 
# Output: [5, 6, 6]

```
---
## 4. Example: Using a Lambda Function

`map()` is most powerful when paired with `lambda` for quick, one-line transformations.

```python
numbers = [1, 2, 3, 4]

# Multiply every number by 10
scaled_numbers = list(map(lambda x: x * 10, numbers))

print(scaled_numbers)
# Output: [10, 20, 30, 40]

```
---
## 5. Why use map() instead of a loop?

* **Performance:** `map()` is written in C and is often faster than a standard `for` loop.
* **Memory Efficiency:** It uses "lazy evaluation." It doesn't compute the whole list at once; it only calculates the next item when you ask for it.
* **Cleanliness:** It makes your intent clear—you are transforming a collection of data from one state to another.

----
⚠️ 3. Lambda
----

## 1. Syntax Breakdown

A lambda function consists of three distinct parts:

| Part | Component | Description |
| --- | --- | --- |
| **1** | `lambda` | The keyword that initializes the function. |
| **2** | `parameters` | The input variables (e.g., `num` or `x, y`). |
| **3** | `operation` | The single line of code that is executed and **automatically returned**. |

**Example: Squaring a number**

```python
# Lambda syntax
lambda num : num ** 2

# Regular function equivalent
def square(num):
    return num ** 2

```

---

## 2. Key Characteristics

* **Single Line:** Lambda functions must be written on one line.
* **No `return` Keyword:** They automatically return the result of the operation.
* **Anonymous:** They don't have a name unless you explicitly assign them to a variable.
* **Multiple Arguments:** You can have more than one parameter by separating them with commas: `lambda x, y : x + y`.

---

## 3. Why use them?

Lambda functions are ideal for **Higher-Order Functions**—functions that take other functions as arguments. They keep your code clean by avoiding the need to define a formal function that you only use once.

### Common Built-in Higher-Order Functions

#### **`map()`**

Applies an operation to **every item** in a list.

```python
nums = [1, 2, 3, 4]
cubes = list(map(lambda x: x**3, nums))
# Result: [1, 8, 27, 64]

```

#### **`filter()`**

Creates a new list containing only items that **meet a condition** (where the lambda returns `True`).

```python
nums = [1, 2, 3, 4, 5, 6]
evens = list(filter(lambda x: x % 2 == 0, nums))
# Result: [2, 4, 6]

```
