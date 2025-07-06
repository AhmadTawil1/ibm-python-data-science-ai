# Python Programming Fundamentals

## 📚 Module Overview

This module covers the essential programming fundamentals in Python, providing a solid foundation for data science and AI applications. You'll learn advanced function concepts, object-oriented programming, exception handling, and text analysis techniques.

## 🎯 Learning Objectives

By the end of this module, you will be able to:

- Write efficient and reusable functions with advanced features
- Implement object-oriented programming principles
- Handle exceptions and errors gracefully
- Perform text analysis and natural language processing
- Apply best practices in Python programming
- Debug and troubleshoot code effectively

## 📁 Module Contents

### 1. [Functions](./functions.ipynb)
**Advanced function concepts and functional programming**

**Topics Covered:**
- Function definition and calling
- Parameters and arguments (positional, keyword, default)
- Variable scope and namespaces
- Lambda functions and anonymous functions
- Decorators and function wrappers
- Recursion and recursive functions
- Higher-order functions
- Function annotations and type hints

**Key Skills:**
- Write clean, reusable functions
- Implement functional programming patterns
- Use decorators for code enhancement
- Handle complex parameter scenarios

### 2. [Object-Oriented Programming](./oop.ipynb)
**Classes, objects, and OOP principles**

**Topics Covered:**
- Classes and objects
- Attributes and methods
- Constructors and initialization
- Inheritance and polymorphism
- Encapsulation and abstraction
- Class methods and static methods
- Property decorators
- Design patterns in Python

**Key Skills:**
- Design and implement classes
- Apply inheritance hierarchies
- Use polymorphism effectively
- Implement encapsulation principles

### 3. [Exception Handling](./exception_handling.ipynb)
**Error management and debugging techniques**

**Topics Covered:**
- Try-except blocks
- Exception types and hierarchy
- Custom exception classes
- Finally and else clauses
- Context managers (with statements)
- Logging and debugging
- Best practices for error handling
- Assertions and testing

**Key Skills:**
- Handle exceptions gracefully
- Create custom exception classes
- Implement proper error logging
- Debug code effectively

### 4. [Text Analysis](./text-analysis.ipynb)
**Natural language processing and text manipulation**

**Topics Covered:**
- String manipulation and formatting
- Regular expressions (regex)
- Text preprocessing techniques
- Tokenization and stemming
- Frequency analysis
- Basic NLP concepts
- Text cleaning and normalization
- Pattern matching and extraction

**Key Skills:**
- Process and analyze text data
- Use regular expressions effectively
- Implement text preprocessing pipelines
- Perform basic NLP tasks

## 🛠️ Prerequisites

- Basic Python syntax knowledge
- Understanding of variables and data types
- Familiarity with control structures (if/else, loops)
- Jupyter Notebook environment

## 📦 Required Libraries

```python
# Core libraries
import re
import logging
import unittest
from typing import List, Dict, Any

# Text processing
import nltk
from nltk.tokenize import word_tokenize
from nltk.stem import PorterStemmer
from nltk.corpus import stopwords

# Data manipulation
import pandas as pd
import numpy as np

# Visualization (optional)
import matplotlib.pyplot as plt
import seaborn as sns
```

## 🚀 Getting Started

1. **Navigate to this directory**:
   ```bash
   cd python-programming-fundamentals
   ```

2. **Install required packages**:
   ```bash
   pip install nltk pandas numpy matplotlib seaborn
   ```

3. **Download NLTK data** (for text analysis):
   ```python
   import nltk
   nltk.download('punkt')
   nltk.download('stopwords')
   nltk.download('averaged_perceptron_tagger')
   ```

4. **Start with functions.ipynb** and progress sequentially

## 📖 Learning Path

### Week 1: Functions and Functional Programming
- **Day 1-2**: Basic functions and parameters
- **Day 3-4**: Advanced function concepts (decorators, lambdas)
- **Day 5-7**: Functional programming patterns

### Week 2: Object-Oriented Programming
- **Day 1-2**: Classes and objects basics
- **Day 3-4**: Inheritance and polymorphism
- **Day 5-7**: Advanced OOP concepts and design patterns

### Week 3: Exception Handling and Debugging
- **Day 1-2**: Try-except blocks and exception types
- **Day 3-4**: Custom exceptions and context managers
- **Day 5-7**: Logging and debugging techniques

### Week 4: Text Analysis
- **Day 1-2**: String manipulation and regex
- **Day 3-4**: Text preprocessing and tokenization
- **Day 5-7**: NLP concepts and applications

## 💡 Key Concepts

### Functions
```python
# Example: Decorator pattern
def timer(func):
    def wrapper(*args, **kwargs):
        import time
        start = time.time()
        result = func(*args, **kwargs)
        end = time.time()
        print(f"{func.__name__} took {end - start:.4f} seconds")
        return result
    return wrapper

@timer
def slow_function():
    import time
    time.sleep(1)
    return "Done!"
```

### Object-Oriented Programming
```python
# Example: Class with inheritance
class Animal:
    def __init__(self, name):
        self.name = name
    
    def speak(self):
        pass

class Dog(Animal):
    def speak(self):
        return f"{self.name} says Woof!"
```

### Exception Handling
```python
# Example: Custom exception
class DataValidationError(Exception):
    def __init__(self, message, data=None):
        super().__init__(message)
        self.data = data

def validate_age(age):
    if not isinstance(age, int) or age < 0:
        raise DataValidationError("Age must be a positive integer", age)
    return age
```

### Text Analysis
```python
# Example: Text preprocessing
import re
from nltk.tokenize import word_tokenize
from nltk.corpus import stopwords

def preprocess_text(text):
    # Convert to lowercase
    text = text.lower()
    # Remove special characters
    text = re.sub(r'[^a-zA-Z\s]', '', text)
    # Tokenize
    tokens = word_tokenize(text)
    # Remove stopwords
    stop_words = set(stopwords.words('english'))
    tokens = [token for token in tokens if token not in stop_words]
    return tokens
```

## 🎓 Assessment Criteria

### Functions Module
- [ ] Write functions with various parameter types
- [ ] Implement decorators for function enhancement
- [ ] Use lambda functions appropriately
- [ ] Apply functional programming concepts

### OOP Module
- [ ] Design and implement classes
- [ ] Use inheritance and polymorphism
- [ ] Apply encapsulation principles
- [ ] Implement design patterns

### Exception Handling Module
- [ ] Handle exceptions with try-except blocks
- [ ] Create custom exception classes
- [ ] Use context managers effectively
- [ ] Implement proper logging

### Text Analysis Module
- [ ] Manipulate strings and use regex
- [ ] Preprocess text data
- [ ] Perform tokenization and stemming
- [ ] Analyze text patterns and frequencies

## 🔧 Best Practices

### Code Organization
- Follow PEP 8 style guidelines
- Use meaningful variable and function names
- Write comprehensive docstrings
- Keep functions focused and single-purpose

### Error Handling
- Always handle potential exceptions
- Provide meaningful error messages
- Use logging for debugging
- Implement graceful degradation

### Performance
- Use appropriate data structures
- Avoid unnecessary computations
- Profile code for bottlenecks
- Optimize critical sections

## 📊 Projects and Exercises

### Mini-Projects
1. **Function Library**: Create a utility library with commonly used functions
2. **Class Hierarchy**: Design a class hierarchy for a specific domain
3. **Error Handler**: Build a comprehensive error handling system
4. **Text Analyzer**: Create a text analysis tool with multiple features

### Exercises
- Function decorators for caching and timing
- Class design for data structures
- Exception handling in file operations
- Text preprocessing pipeline

## 🆘 Troubleshooting

### Common Issues
1. **Import Errors**: Ensure all required packages are installed
2. **NLTK Data**: Download required NLTK datasets
3. **Jupyter Issues**: Restart kernel if cells don't execute properly
4. **Memory Issues**: Use generators for large datasets

### Debugging Tips
- Use `print()` statements for quick debugging
- Implement logging for complex issues
- Use Python debugger (pdb) for step-by-step debugging
- Check variable types with `type()` function

## 📚 Additional Resources

### Documentation
- [Python Official Documentation](https://docs.python.org/)
- [NLTK Documentation](https://www.nltk.org/)
- [PEP 8 Style Guide](https://www.python.org/dev/peps/pep-0008/)

### Books
- "Fluent Python" by Luciano Ramalho
- "Python Cookbook" by David Beazley
- "Natural Language Processing with Python" by Steven Bird

### Online Courses
- Python for Data Science (Coursera)
- Advanced Python Programming (edX)
- Natural Language Processing (Stanford)

## 🎯 Next Steps

After completing this module:
- Move to **Python Data Structures** for advanced data manipulation
- Explore **Python APIs and Data Collection** for external data access
- Continue with **Python Working with Data** for analysis tools

---

**Ready to master Python fundamentals? Let's get started! 🐍✨** 