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

**Would you like me to generate some Python code examples showing how to convert between these three types?**
