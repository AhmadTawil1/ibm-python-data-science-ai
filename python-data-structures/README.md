# Python Data Structures

## 📚 Module Overview

This module explores the fundamental data structures in Python, providing deep understanding of lists, tuples, dictionaries, and sets. You'll learn when and how to use each data structure effectively, understand their performance characteristics, and apply them to solve real-world problems in data science and AI.

## 🎯 Learning Objectives

By the end of this module, you will be able to:

- Understand the characteristics and use cases of each data structure
- Choose the appropriate data structure for specific problems
- Analyze time and space complexity of operations
- Implement efficient algorithms using Python data structures
- Apply data structures to data science and AI problems
- Optimize code performance through proper data structure selection

## 📁 Module Contents

### 1. [Lists](./lists.ipynb)
**Dynamic arrays and list operations**

**Topics Covered:**
- List creation and initialization
- List indexing and slicing
- List methods and operations
- List comprehensions
- Nested lists and 2D arrays
- Performance characteristics
- Memory management
- Advanced list operations

**Key Skills:**
- Manipulate lists efficiently
- Use list comprehensions for data transformation
- Handle nested data structures
- Optimize list operations for performance

### 2. [Tuples](./tuples.ipynb)
**Immutable sequences and their applications**

**Topics Covered:**
- Tuple creation and properties
- Immutability and its benefits
- Tuple unpacking and assignment
- Named tuples (collections.namedtuple)
- Tuple methods and operations
- Use cases for tuples
- Performance vs lists
- Tuple as dictionary keys

**Key Skills:**
- Use tuples for immutable data
- Implement tuple unpacking effectively
- Create named tuples for structured data
- Choose between tuples and lists appropriately

### 3. [Dictionaries](./dictionaries.ipynb)
**Key-value pairs and hash tables**

**Topics Covered:**
- Dictionary creation and manipulation
- Dictionary methods and operations
- Dictionary comprehensions
- Nested dictionaries
- Hash table implementation
- Dictionary performance characteristics
- Default dictionaries (collections.defaultdict)
- Ordered dictionaries (collections.OrderedDict)

**Key Skills:**
- Design efficient key-value data structures
- Use dictionary comprehensions
- Handle nested dictionary structures
- Optimize dictionary operations

### 4. [Sets](./sets.ipynb)
**Unique collections and set operations**

**Topics Covered:**
- Set creation and properties
- Set operations (union, intersection, difference)
- Set comprehensions
- Frozen sets (immutable sets)
- Set methods and operations
- Mathematical set operations
- Performance characteristics
- Use cases in data science

**Key Skills:**
- Perform set operations efficiently
- Use sets for duplicate removal
- Implement mathematical set operations
- Apply sets to data analysis problems

## 🛠️ Prerequisites

- Basic Python syntax knowledge
- Understanding of variables and data types
- Familiarity with control structures
- Completion of Python Programming Fundamentals module

## 📦 Required Libraries

```python
# Core libraries
import time
import sys
from collections import defaultdict, OrderedDict, namedtuple
from typing import List, Tuple, Dict, Set, Any

# Data manipulation
import numpy as np
import pandas as pd

# Visualization (optional)
import matplotlib.pyplot as plt
import seaborn as sns

# Performance analysis
from memory_profiler import profile
```

## 🚀 Getting Started

1. **Navigate to this directory**:
   ```bash
   cd python-data-structures
   ```

2. **Install required packages**:
   ```bash
   pip install numpy pandas matplotlib seaborn memory-profiler
   ```

3. **Start with lists.ipynb** and progress sequentially

## 📖 Learning Path

### Week 1: Lists and Dynamic Arrays
- **Day 1-2**: Basic list operations and methods
- **Day 3-4**: List comprehensions and advanced operations
- **Day 5-7**: Performance analysis and optimization

### Week 2: Tuples and Immutability
- **Day 1-2**: Tuple basics and immutability
- **Day 3-4**: Named tuples and tuple unpacking
- **Day 5-7**: Use cases and performance comparison

### Week 3: Dictionaries and Hash Tables
- **Day 1-2**: Dictionary operations and methods
- **Day 3-4**: Dictionary comprehensions and nested structures
- **Day 5-7**: Advanced dictionary types and optimization

### Week 4: Sets and Mathematical Operations
- **Day 1-2**: Set operations and properties
- **Day 3-4**: Set comprehensions and frozen sets
- **Day 5-7**: Applications in data science

## 💡 Key Concepts

### Lists - Dynamic Arrays
```python
# List comprehension example
numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
squares = [x**2 for x in numbers if x % 2 == 0]
# Result: [4, 16, 36, 64, 100]

# Nested list comprehension
matrix = [[i+j for j in range(3)] for i in range(3)]
# Result: [[0, 1, 2], [1, 2, 3], [2, 3, 4]]
```

### Tuples - Immutable Sequences
```python
# Named tuple example
from collections import namedtuple
Point = namedtuple('Point', ['x', 'y'])
p = Point(3, 4)
print(p.x, p.y)  # 3 4

# Tuple unpacking
coordinates = (10, 20)
x, y = coordinates
print(f"X: {x}, Y: {y}")  # X: 10, Y: 20
```

### Dictionaries - Hash Tables
```python
# Dictionary comprehension
word_counts = {'hello': 5, 'world': 3, 'python': 8}
filtered_counts = {word: count for word, count in word_counts.items() if count > 4}
# Result: {'hello': 5, 'python': 8}

# Default dictionary
from collections import defaultdict
dd = defaultdict(list)
dd['fruits'].append('apple')
dd['fruits'].append('banana')
# No need to check if key exists
```

### Sets - Unique Collections
```python
# Set operations
set1 = {1, 2, 3, 4, 5}
set2 = {4, 5, 6, 7, 8}

union = set1 | set2  # or set1.union(set2)
intersection = set1 & set2  # or set1.intersection(set2)
difference = set1 - set2  # or set1.difference(set2)

# Set comprehension
vowels = {'a', 'e', 'i', 'o', 'u'}
text = "hello world"
unique_vowels = {char for char in text if char in vowels}
# Result: {'e', 'o'}
```

## ⏱️ Performance Characteristics

### Time Complexity Comparison

| Operation | List | Tuple | Dictionary | Set |
|-----------|------|-------|------------|-----|
| Access by index/key | O(1) | O(1) | O(1) | N/A |
| Search | O(n) | O(n) | O(1) | O(1) |
| Insertion | O(1) | N/A | O(1) | O(1) |
| Deletion | O(n) | N/A | O(1) | O(1) |
| Append | O(1) | N/A | N/A | N/A |

### Memory Usage
```python
import sys

# Memory comparison
list_example = [1, 2, 3, 4, 5]
tuple_example = (1, 2, 3, 4, 5)
dict_example = {1: 'a', 2: 'b', 3: 'c', 4: 'd', 5: 'e'}
set_example = {1, 2, 3, 4, 5}

print(f"List memory: {sys.getsizeof(list_example)} bytes")
print(f"Tuple memory: {sys.getsizeof(tuple_example)} bytes")
print(f"Dict memory: {sys.getsizeof(dict_example)} bytes")
print(f"Set memory: {sys.getsizeof(set_example)} bytes")
```

## 🎓 Assessment Criteria

### Lists Module
- [ ] Create and manipulate lists efficiently
- [ ] Use list comprehensions for data transformation
- [ ] Handle nested list structures
- [ ] Analyze list performance characteristics

### Tuples Module
- [ ] Use tuples for immutable data
- [ ] Implement tuple unpacking effectively
- [ ] Create and use named tuples
- [ ] Choose between tuples and lists appropriately

### Dictionaries Module
- [ ] Design efficient key-value data structures
- [ ] Use dictionary comprehensions
- [ ] Handle nested dictionary structures
- [ ] Optimize dictionary operations

### Sets Module
- [ ] Perform set operations efficiently
- [ ] Use sets for duplicate removal
- [ ] Implement mathematical set operations
- [ ] Apply sets to data analysis problems

## 🔧 Best Practices

### Data Structure Selection
- **Use Lists** for ordered, mutable sequences
- **Use Tuples** for immutable, ordered data
- **Use Dictionaries** for key-value mappings
- **Use Sets** for unique collections and mathematical operations

### Performance Optimization
- Choose the right data structure for your use case
- Use comprehensions for cleaner, faster code
- Avoid unnecessary conversions between data structures
- Profile your code to identify bottlenecks

### Memory Management
- Be aware of memory overhead of different structures
- Use generators for large datasets
- Clean up references when no longer needed
- Monitor memory usage in production systems

## 📊 Projects and Exercises

### Mini-Projects
1. **Data Structure Benchmark**: Compare performance of different structures
2. **Custom Data Structure**: Implement a specialized data structure
3. **Data Analysis Tool**: Build tools using various data structures
4. **Memory Profiler**: Create a tool to analyze memory usage

### Exercises
- Implement a cache using dictionaries
- Create a frequency counter using defaultdict
- Build a graph representation using nested dictionaries
- Design a data validation system using sets

## 🆘 Troubleshooting

### Common Issues
1. **Mutable vs Immutable**: Remember that tuples are immutable
2. **Hashable Keys**: Dictionary keys must be hashable
3. **Memory Usage**: Large data structures can consume significant memory
4. **Performance**: Choose appropriate data structures for your use case

### Debugging Tips
- Use `type()` to check data structure types
- Print data structure contents for debugging
- Use `sys.getsizeof()` to check memory usage
- Profile code performance with `timeit` module

## 📚 Additional Resources

### Documentation
- [Python Data Structures](https://docs.python.org/3/tutorial/datastructures.html)
- [Collections Module](https://docs.python.org/3/library/collections.html)
- [Time Complexity](https://wiki.python.org/moin/TimeComplexity)

### Books
- "Python Data Structures and Algorithms" by Benjamin Baka
- "Problem Solving with Algorithms and Data Structures" by Brad Miller
- "High Performance Python" by Micha Gorelick

### Online Resources
- [Big-O Complexity Chart](https://www.bigocheatsheet.com/)
- [Python Data Structures Tutorial](https://realpython.com/python-data-structures/)
- [Collections Module Guide](https://pymotw.com/3/collections/)

## 🎯 Next Steps

After completing this module:
- Move to **Python APIs and Data Collection** for external data access
- Explore **Python Working with Data** for advanced data manipulation
- Consider learning about custom data structures and algorithms

## 🔍 Real-World Applications

### Data Science Applications
- **Lists**: Time series data, feature vectors
- **Tuples**: Data records, coordinates, RGB values
- **Dictionaries**: Configuration settings, API responses
- **Sets**: Unique identifiers, category labels

### AI/ML Applications
- **Lists**: Training data, model parameters
- **Tuples**: Data points, model outputs
- **Dictionaries**: Model hyperparameters, feature mappings
- **Sets**: Vocabulary, unique classes

---

**Master the building blocks of Python programming! 🏗️🐍** 