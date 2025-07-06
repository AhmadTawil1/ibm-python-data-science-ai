# Python Working with Data

## 📚 Module Overview

This module focuses on data manipulation and analysis using Python's most powerful data science libraries. You'll learn to work with files, perform numerical computing with NumPy, and analyze data with Pandas. These skills are fundamental for any data science or AI project.

## 🎯 Learning Objectives

By the end of this module, you will be able to:

- Read and write various file formats (CSV, JSON, Excel, etc.)
- Perform efficient numerical computations with NumPy
- Manipulate and analyze data using Pandas DataFrames
- Clean and preprocess data for analysis
- Create visualizations and reports
- Handle large datasets efficiently
- Apply data analysis techniques to real-world problems
- Build data processing pipelines

## 📁 Module Contents

### 1. [File Operations](./files-read.ipynb & ./files-write.ipynb)
**Reading and writing different file formats**

**Topics Covered:**
- File handling fundamentals
- Reading and writing CSV files
- Working with JSON data
- Excel file operations
- Text file processing
- Binary file handling
- File encoding and decoding
- Error handling in file operations

**Key Skills:**
- Handle various file formats efficiently
- Implement proper error handling
- Work with different data encodings
- Build robust file processing pipelines

### 2. [NumPy 1D Arrays](./numpy1d.ipynb)
**One-dimensional array operations and mathematical functions**

**Topics Covered:**
- NumPy array creation and manipulation
- Array indexing and slicing
- Mathematical operations and functions
- Statistical functions
- Array broadcasting
- Memory management
- Performance optimization
- Random number generation

**Key Skills:**
- Create and manipulate NumPy arrays
- Perform mathematical operations efficiently
- Use statistical functions for data analysis
- Optimize array operations for performance

### 3. [NumPy 2D Arrays](./numpy2D.ipynb)
**Multi-dimensional arrays and matrix operations**

**Topics Covered:**
- 2D array creation and manipulation
- Matrix operations and linear algebra
- Array reshaping and transposition
- Broadcasting with multiple dimensions
- Advanced indexing techniques
- Performance considerations
- Memory layout and optimization
- Integration with other libraries

**Key Skills:**
- Work with multi-dimensional arrays
- Perform matrix operations efficiently
- Apply linear algebra concepts
- Optimize memory usage for large arrays

### 4. [Pandas DataFrames](./pandas_loading_data.ipynb, ./pandas_practice.ipynb, ./pandas-test.ipynb)
**Data manipulation and analysis with Pandas**

**Topics Covered:**
- DataFrame creation and manipulation
- Data loading from various sources
- Data cleaning and preprocessing
- Data filtering and selection
- Grouping and aggregation
- Merging and joining data
- Time series analysis
- Data visualization with Pandas

**Key Skills:**
- Create and manipulate DataFrames
- Clean and preprocess data effectively
- Perform complex data analysis
- Create informative visualizations

## 🛠️ Prerequisites

- Basic Python programming knowledge
- Understanding of data structures (lists, dictionaries)
- Familiarity with mathematical concepts
- Completion of previous modules recommended

## 📦 Required Libraries

```python
# Core data science libraries
import numpy as np
import pandas as pd

# File handling
import csv
import json
import pickle
import openpyxl
import xlrd

# Visualization
import matplotlib.pyplot as plt
import seaborn as sns
import plotly.express as px
import plotly.graph_objects as go

# Scientific computing
from scipy import stats
from scipy import linalg

# Utilities
import os
import glob
from pathlib import Path
from typing import List, Dict, Any, Optional
import warnings
warnings.filterwarnings('ignore')
```

## 🚀 Getting Started

1. **Navigate to this directory**:
   ```bash
   cd python-working-with-data
   ```

2. **Install required packages**:
   ```bash
   pip install numpy pandas matplotlib seaborn plotly scipy openpyxl xlrd
   ```

3. **Set up your environment**:
   ```python
   # Set display options for better output
   pd.set_option('display.max_columns', None)
   pd.set_option('display.max_rows', 100)
   pd.set_option('display.width', 1000)
   ```

4. **Start with files-read.ipynb** and progress sequentially

## 📖 Learning Path

### Week 1: File Operations
- **Day 1-2**: Basic file handling and CSV operations
- **Day 3-4**: JSON and Excel file processing
- **Day 5-7**: Advanced file operations and error handling

### Week 2: NumPy 1D Arrays
- **Day 1-2**: Array creation and basic operations
- **Day 3-4**: Mathematical and statistical functions
- **Day 5-7**: Broadcasting and performance optimization

### Week 3: NumPy 2D Arrays
- **Day 1-2**: Multi-dimensional arrays and indexing
- **Day 3-4**: Matrix operations and linear algebra
- **Day 5-7**: Advanced operations and optimization

### Week 4: Pandas DataFrames
- **Day 1-2**: DataFrame creation and basic operations
- **Day 3-4**: Data cleaning and preprocessing
- **Day 5-7**: Advanced analysis and visualization

## 💡 Key Concepts

### File Operations
```python
import pandas as pd
import json

# Reading CSV files
df = pd.read_csv('data.csv', encoding='utf-8')

# Reading JSON files
with open('data.json', 'r') as f:
    data = json.load(f)

# Writing to different formats
df.to_csv('output.csv', index=False)
df.to_json('output.json', orient='records')
df.to_excel('output.xlsx', sheet_name='Data')
```

### NumPy 1D Arrays
```python
import numpy as np

# Array creation
arr = np.array([1, 2, 3, 4, 5])
zeros = np.zeros(10)
ones = np.ones(5)
range_arr = np.arange(0, 10, 2)

# Mathematical operations
mean_val = np.mean(arr)
std_val = np.std(arr)
sum_val = np.sum(arr)

# Broadcasting
arr * 2  # Multiply all elements by 2
arr + 10  # Add 10 to all elements
```

### NumPy 2D Arrays
```python
import numpy as np

# 2D array creation
matrix = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])
zeros_matrix = np.zeros((3, 4))
identity = np.eye(3)

# Matrix operations
transpose = matrix.T
determinant = np.linalg.det(matrix)
inverse = np.linalg.inv(matrix)

# Advanced indexing
subset = matrix[0:2, 1:3]
```

### Pandas DataFrames
```python
import pandas as pd
import numpy as np

# DataFrame creation
data = {
    'Name': ['Alice', 'Bob', 'Charlie'],
    'Age': [25, 30, 35],
    'Salary': [50000, 60000, 70000]
}
df = pd.DataFrame(data)

# Data manipulation
df['Bonus'] = df['Salary'] * 0.1
filtered_df = df[df['Age'] > 28]
grouped = df.groupby('Age')['Salary'].mean()

# Data cleaning
df.dropna()  # Remove missing values
df.fillna(0)  # Fill missing values with 0
```

## 📊 Data Analysis Workflow

### 1. Data Loading
```python
# Load data from various sources
df = pd.read_csv('data.csv')
df_json = pd.read_json('data.json')
df_excel = pd.read_excel('data.xlsx')
```

### 2. Data Exploration
```python
# Basic information
print(df.info())
print(df.describe())
print(df.head())
print(df.shape)

# Check for missing values
print(df.isnull().sum())

# Unique values
print(df['column'].unique())
print(df['column'].value_counts())
```

### 3. Data Cleaning
```python
# Handle missing values
df = df.dropna()  # or df.fillna(method='ffill')

# Remove duplicates
df = df.drop_duplicates()

# Data type conversion
df['date'] = pd.to_datetime(df['date'])
df['category'] = df['category'].astype('category')

# String cleaning
df['text'] = df['text'].str.strip().str.lower()
```

### 4. Data Analysis
```python
# Statistical analysis
summary = df.groupby('category').agg({
    'value': ['mean', 'std', 'count']
})

# Correlation analysis
correlation_matrix = df.corr()

# Time series analysis
df.set_index('date', inplace=True)
monthly_avg = df.resample('M').mean()
```

### 5. Visualization
```python
import matplotlib.pyplot as plt
import seaborn as sns

# Basic plots
plt.figure(figsize=(10, 6))
df['value'].hist(bins=30)
plt.title('Distribution of Values')
plt.show()

# Correlation heatmap
sns.heatmap(correlation_matrix, annot=True, cmap='coolwarm')
plt.show()

# Time series plot
df['value'].plot()
plt.title('Time Series Analysis')
plt.show()
```

## 🔧 Best Practices

### Performance Optimization
```python
# Use NumPy for numerical operations
# Instead of Python loops
result = np.sum(array)  # Fast
result = sum(array)     # Slower

# Use vectorized operations in Pandas
# Instead of apply() when possible
df['new_col'] = df['col1'] + df['col2']  # Fast
df['new_col'] = df.apply(lambda x: x['col1'] + x['col2'], axis=1)  # Slower

# Use appropriate data types
df['category'] = df['category'].astype('category')  # Memory efficient
```

### Memory Management
```python
# Monitor memory usage
print(df.memory_usage(deep=True))

# Use chunking for large files
chunk_size = 10000
for chunk in pd.read_csv('large_file.csv', chunksize=chunk_size):
    process_chunk(chunk)

# Clean up memory
import gc
del large_dataframe
gc.collect()
```

### Error Handling
```python
# Safe file reading
try:
    df = pd.read_csv('data.csv')
except FileNotFoundError:
    print("File not found")
except pd.errors.EmptyDataError:
    print("File is empty")
except Exception as e:
    print(f"Error: {e}")

# Data validation
assert df['age'].min() >= 0, "Age cannot be negative"
assert df['salary'].dtype == 'float64', "Salary must be numeric"
```

## 📊 Projects and Exercises

### Mini-Projects
1. **Data Cleaning Pipeline**: Build a comprehensive data cleaning system
2. **Financial Data Analysis**: Analyze stock market data
3. **Customer Analytics**: Analyze customer behavior data
4. **Time Series Analysis**: Work with temporal data

### Exercises
- Clean a messy dataset with missing values and duplicates
- Perform statistical analysis on a dataset
- Create visualizations for data insights
- Build a data processing pipeline

## 🆘 Troubleshooting

### Common Issues
1. **Memory Errors**: Use chunking for large datasets
2. **Data Type Issues**: Check and convert data types appropriately
3. **Missing Values**: Handle missing data systematically
4. **Performance Issues**: Use vectorized operations instead of loops

### Debugging Tips
- Use `df.info()` to check data types and memory usage
- Use `df.isnull().sum()` to identify missing values
- Use `df.describe()` to understand data distribution
- Use `df.head()` and `df.tail()` to inspect data

## 📚 Additional Resources

### Documentation
- [NumPy Documentation](https://numpy.org/doc/)
- [Pandas Documentation](https://pandas.pydata.org/docs/)
- [Matplotlib Documentation](https://matplotlib.org/)
- [Seaborn Documentation](https://seaborn.pydata.org/)

### Books
- "Python for Data Analysis" by Wes McKinney
- "NumPy Beginner's Guide" by Ivan Idris
- "Data Science Handbook" by Jake VanderPlas

### Online Courses
- DataCamp's Python for Data Science
- Coursera's Applied Data Science with Python
- edX's Python for Data Science

## 🎯 Next Steps

After completing this module:
- Explore machine learning with scikit-learn
- Learn advanced visualization with Plotly and Bokeh
- Study deep learning with TensorFlow or PyTorch
- Consider big data processing with Apache Spark

## 🔍 Real-World Applications

### Data Science Applications
- **Exploratory Data Analysis**: Understanding data patterns and relationships
- **Data Cleaning**: Preparing data for machine learning models
- **Statistical Analysis**: Performing hypothesis testing and inference
- **Time Series Analysis**: Analyzing temporal data patterns

### Business Applications
- **Financial Analysis**: Analyzing market data and trends
- **Customer Analytics**: Understanding customer behavior and preferences
- **Sales Analysis**: Tracking performance and identifying opportunities
- **Quality Control**: Monitoring and analyzing process data

---

**Ready to become a data manipulation expert? Let's analyze some data! 📈🔍** 